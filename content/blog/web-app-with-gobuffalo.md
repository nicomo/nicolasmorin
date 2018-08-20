+++
title = "Web App With Gobuffalo"
date = 2018-08-19T17:05:51+02:00
description = "Building a mock web app to learn the ins & outs of the GoBuffalo web framework"
tags = [ "golang", "gobuffalo",  ]
type = "post"
image = "img/kumano-kodo.jpg"
+++

Two years ago I started [learning the Go Programming language](https://www.nicolasmorin.com/blog/learning-go/). I'm not a professional dev and so couldn't devote as much time to it as I would have liked, but I did continue to learn and got better at it.

One of the issues I outlined in the post linked above from 2 years ago as I was beginning, was that I didn't find a Go web framework I liked, but [https://gobuffalo.io](https://gobuffalo.io) has emerged in the meantime. It is inspired by Ruby on Rails, the documentation says. But I don't know Ruby on Rails, so what's meaningful to me is that Buffalo:

- uses the Model-View-Controller paradigm and organizes your code accordingly
- is also a toolbox, and thus provides many tools to help you with common tasks / patterns in a web application.

That all seemed promising, so I thought I could use the summer holiday to give it a spin and learn how it works. Hence this post about the mock blogging platform I coded, just to learn the ins and out of the framework. I won't cover the basics of installing Buffalo and creating a new project, see: [https://gobuffalo.io/en/docs/installation](https://gobuffalo.io/en/docs/installation). We'll start from there.

## Goals for the Users

For my users I wanted something a bit more involved than the usual example of a form to register an account.

My social network is invitations-only : current users (that would only be user #1 at the outset) can invite a certain number of people to join the network, by registering their email addresses. Those users receive an email, which contains a unique token. When they click on the link and get to our site, the token is tested and if validated, they can complete their registration. But again, not through a form : using their twitter or github account only (OAuth).

Also, I had this idea that users have _points_: they're rewarded for good behavior on the site. They get or lose points when they post, when they log in, when they don't log in on consecutive days, when their posts are starred, or flagged. Something like your [reputation on Stack Overflow](https://stackoverflow.com/help/whats-reputation) (_it's never been clear to me why generalist social networks don't use such a system, but that's another subject_).

Buffalo has **generators**. The most general one is ```buffalo generate resource users```

## Models & DB migration

The generate command above will create a ```models/user.go``` file that contains the base struct for our users and a bunch of functions to read/write users in the database : ```ValidateCreate```, ```ValidateUpdate```, etc.

It will also create 2 files for migrating the database up or down under migrations/.

I completed the user struct first, then the migration file. Here's my struct.

```
type User struct {
	ID                uuid.UUID    `json:"id" db:"id"`
	CreatedAt         time.Time    `json:"created_at" db:"created_at"`
	UpdatedAt         time.Time    `json:"updated_at" db:"updated_at"`
	AvatarURL         nulls.String `json:"avatar_url" db:"avatar_url"`
	Bio               nulls.String `json:"bio" db:"bio"`
	Email             nulls.String `json:"email" db:"email"`
	InvitationToken   string       `json:"invitation_token" db:"invitation_token"`
	InvitedAt         time.Time    `json:"invited_at" db:"invited_at"`
	IsAdmin           bool         `json:"is_admin" db:"is_admin"`
	LastLoggedAt      time.Time    `json:"last_logged_at" db:"last_logged_at"`
	LastPostedAt      time.Time    `json:"last_posted_at" db:"last_posted_at"`
	Name              nulls.String `json:"name" db:"name"`
	Nickname          nulls.String `json:"nickname" db:"nickname"`
	Provider          nulls.String `json:"provider" db:"provider"`
	ProviderID        nulls.String `json:"provider_id" db:"provider_id"`
	Score             int          `json:"score" db:"score"`
	SignedUpAt        time.Time    `json:"signedup_at" db:"signedup_at"`
	SponsorshipsCount int          `json:"sponsorships_count" db:"sponsorships_count"`
	SponsorID         uuid.UUID    `json:"sponsor_id" db:"sponsor_id"`
	Sponsoring        Users        `has_many:"users"`
	Texts             Texts        `has_many:"texts" order_by:"created_at desc"`
	Starred           Texts        `many_to_many:"stars" db:"-"`
}
```
A few comments here : 

- ID, CreatedAt and UpdatedAt were provided by the generate command
- [uuid](https://github.com/gobuffalo/uuid) creates the unique ID. It's a Buffalo sub-package. So is [nulls](https://github.com/gobuffalo/pop/tree/master/nulls), which replaces the built-in null types in the sql package and is used by pop, the included ORM. 
- tags are used by Buffalo to match struct fields to the db, they can be named, ignored, they can point to associations in the db, things like ```has_many``` or ```many_to_many```.

And here's the corresponding migration file, with the indexes.

```
create_table("users", func(t) {
	t.Column("avatar_url", "string", {"null": true})
	t.Column("bio", "text", {"null": true})
	t.Column("email", "string", {"null": true})
	t.Column("id", "uuid", {"primary": true})
	t.Column("invitation_token", "string", {})
	t.Column("invited_at", "timestamptz", {})
	t.Column("is_admin", "boolean", {"default": false})
	t.Column("last_logged_at", "timestamptz", {})
	t.Column("last_posted_at", "timestamptz", {})
	t.Column("name", "string", {"null": true, "size": 50})
	t.Column("nickname", "string", {"null": true, "size": 50})
	t.Column("provider", "string", {"null": true})
	t.Column("provider_id", "string", {"null": true})
	t.Column("score", "integer", {"default": 0})
	t.Column("signedup_at", "timestamptz", {})
	t.Column("sponsor_id", "uuid", {})
	t.Column("sponsorships_count", "integer", {"default": 0})
})

add_index("users", "nickname", {"unique": true})
add_index("users", ["provider", "provider_id"], {"unique": true})
add_index("users", "email", {"unique": true})
```
It's then a matter of typing ```buffalo db migrate up``` for the table to be created.

The process to create the Text struct and the corresponding DB table was the same.

But when I wanted to create the Star struct, which is the db table and the model used for the many to many association between texts and users (when a user _stars_ a text), I didn't want Buffalo to also create templates, actions, etc. I only wanted the model. You can restrict what the generate command will create: ```buffalo generate model stars``` did that and I ended up with only this model

```
type Star struct {
	ID        uuid.UUID `json:"id" db:"id"`
	CreatedAt time.Time `json:"created_at" db:"created_at"`
	UpdatedAt time.Time `json:"updated_at" db:"updated_at"`
	UserID    uuid.UUID `json:"user_id" db:"user_id"`
	TextID    uuid.UUID `json:"text_id" db:"text_id"`
}
```

## Routes and middlewares

Buffalo works with a ```func App() *buffalo.App``` managing all the routing of http requests.
The app ```Use``` function allows one to attach middlewares to the App. Some  are provided by Buffalo itself, like ```app.Use(csrf.New)``` to protect your site against CSRF attacks - other provided middlewares are for wrapping requests to the DB in transactions, managing translation strings, etc. 

I can also provide my own middlewares. 
A simple one might be to check if the user is logged in or not:
```
// LoginRequired middleware checks the user is logged in before accessing route.
func LoginRequired(next buffalo.Handler) buffalo.Handler {
	return func(c buffalo.Context) error {
		_, ok := c.Value("current_user").(*models.User)
		if ok {
			return next(c)
		}
		c.Flash().Add("danger", T.Translate(c, "users.loginrequired"))
		return c.Redirect(302, "/")
	}
}
```

I can then attach the middleware to any route in actions/app.go, where routes are defined, grouped, etc. 

For my users routes I have 

```
// for my users resource
ur := &UsersResource{}
// create a group of routes
usersGroup := app.Group("/users")
// require middleware on all routes in this group
usersGroup.Use(LoginRequired)
// except users Show
usersGroup.Middleware.Skip(LoginRequired, ur.Show)
// link each route to its handler
usersGroup.GET("/", ur.List)
usersGroup.GET("/new", ur.New)
usersGroup.GET("/{user_id}", ur.Show)
usersGroup.GET("/{user_id}/edit", ur.Edit)
usersGroup.POST("/", ur.Create)
usersGroup.PUT("/{user_id}", ur.Update) 
usersGroup.DELETE("/{user_id}", ur.Destroy)
```

It's [Gorilla Mux](https://github.com/gorilla/mux) under the hood, so you can use everything that Gorilla mux allows.

One of the fun middlewares I did was CanPost: my users can only post once every 24 hours; it's a _slow_ platform.

```
// CanPost checks if user has already posted in last 24 hours
func CanPost(user *models.User, next buffalo.Context) buffalo.Context {
	// id est : 1 post per 24 hours max.
	diff := time.Since(user.LastPostedAt)
	if diff.Hours() < 24.0 {
		next.Set("user_can_post", false)
		next.Flash().Add("info", fmt.Sprintf("Slow down (last post was %s ago). You can still work on drafts though.", diff.Truncate(time.Second).String()))
	} else {
		next.Set("user_can_post", true)
	}
	return next
}
```

## Users invitations and account creation

I now have a model/db table for users, basic templates provided by Buffalo and routes, let's create actual users.

### Invitation

Like I said I want an invitation process in 3 steps: 

- logged in user #1 creates a new user #2 in db, entering the email
- user #2 gets an email with an invitation token
- user #2 arrives on our site using the token and completes her account using a third party, here github or twitter.

For step 1, I just used the template for creating a new account, removing all the fields except for email and keeping the route to the users resource ```Create``` func.

That's where the fun is.

```
// Create adds a User to the DB. This function is mapped to the
// path POST /users
func (v UsersResource) Create(c buffalo.Context) error {

	// redirect url
	redirectURL := "users/" + c.Session().Get("current_user_id").(uuid.UUID).String()
```

1st stop: creating a user normally redirects to the just created account afterwards. This is not what I want, I want to get back to the sponsor's page, the user #1 doing the invitation. I get her unique ID from the session.

```
	// Allocate an empty User
	user := &models.User{}

	// Bind user to the html form elements
	if err := c.Bind(user); err != nil {
		return errors.WithStack(err)
	}

	// add invitation token and time + sponsor ID
	invitationToken, err := uuid.NewV4()
	if err != nil {
		fmt.Printf("Couldn't create uuid for invitation token: %s", err)
		return c.Redirect(422, redirectURL)
	}
	user.InvitationToken = invitationToken.String()
	user.InvitedAt = time.Now()
	user.SponsorID = c.Session().Get("current_user_id").(uuid.UUID)
```
I get the email from the form, but I need a few extra information before saving our new user: a unique invitation token, who sponsored the invitation and when.

```
	// Get the DB connection from the context
	tx, ok := c.Value("tx").(*pop.Connection)
	if !ok {
		return errors.WithStack(errors.New("no transaction found"))
	}

	// Validate the data from the html form
	verrs, err := tx.ValidateAndCreate(user, "provider", "provider_id")
	if err != nil {
		return errors.WithStack(err)
	}

	if verrs.HasAny() {
		// Make the errors available inside the html template
		c.Set("errors", verrs)
		// Redirect to sponsor profile
		return c.Redirect(302, redirectURL)
	}
```

I saved our new user #2 to the DB, using the ```ValidateAndCreate``` method, which has a useful list of tests: is the field present, is it more than 2 characters and less than 50, that sort of things. You can customize the list of tests and add your own, such as: is the email well-formed.

```
	// send email to invited user
	sponsor := c.Value("current_user").(*models.User)

	emailData := map[string]string{
		"emailTo":         user.Email.String,
		"invitationURL":   "http://127.0.0.1:3000/auth/invitation/" + user.InvitationToken,
		"sponsorName":     sponsor.Name.String,
		"sponsorNickname": sponsor.Nickname.String,
		"sponsorID":       user.SponsorID.String(),
	}

	if err := mailers.SendInvitation(emailData); err != nil {
		fmt.Print(err)
		c.Flash().Add("danger", T.Translate(c, "users.sendinvitation.failure"))
	} else {
		// If there are no errors set a success message
		c.Flash().Add("success", T.Translate(c, "users.sendinvitation.success"))
	}
```

Here I'm using a nice extension provided by Buffalo, called [mailer](https://gobuffalo.io/en/docs/mail). It's another generator: ```buffalo generate mailer invitation_email```. Once I have it setup, I can use it directly in my code, as you can see above. And finally, you can see how I can use Flash messages to convey messages to the UI, and ```T.Translate``` to manage the different language strings for those messages.

Once user #2 receives the email, she can click on the provided link, which contains her unique token to validate her account. When she gets to /invitation/{token} I can extract the token and retrieve the user associated with this token if any. 
If it's successful in that, user#2 is redirected to a signup page and presented with 2 buttons to complete the process, one for github and one for twitter.

### OAuth

From then on I'm using another provided tool: [Goth](https://github.com/gobuffalo/buffalo-goth), which manages the OAuth process. 

I'm having fun in ```func AuthCallback(c buffalo.Context)```, which I use both for signup and signin with OAuth.
I'm looking users up in the DB with both their provider (_github_) and ID at that provider (_123123007_):

```
q := tx.Where("provider = ? and provider_id = ?", gothUser.Provider, gothUser.UserID)
exists, err := q.Exists("users")
```

If that user already exists, she's signing in. If not, she's signing up. In which case I can populate the user struct with information coming from the OAuth provider, revoke the invitation token and update to DB.

Along the way, I can add my own logic to the process, for instance crediting our new user with 30 points, or calculating the last time our returning user logged in and substracting 1 point per day away from the web app... Good users come everyday, I say.

## Templates

As for the templates, I've stuck to the default provided by Buffalo, i.e. Bootstrap 3 and jQuery.

The default templating system is good enough for me. It uses partials to manage repeating blocks of UI, such as ```<%= partial("header.html") %>```.

It has a nice system of customizable helpers, well [described in the documentation](https://gobuffalo.io/en/docs/helpers), which allowed to do things like this on a user's profile:

```
<%= if (is_admin()) { %>
    <ul>
        <li>ID: <%= user.ID %></li>
        <li>Provider: <%= user.Provider %>/<%= user.ProviderID %></li>
        <li>CreatedAt: <%= user.CreatedAt %></li>
        <li>InvitedAt: <%= user.InvitedAt %></li>
        <li>SignedUpAt: <%= user.SignedUpAt %></li>
        <li>UpdatedAt: <%= user.UpdatedAt %></li>
        <li>LastPostedAt: <%= user.LastPostedAt %></li>
        <li>LastLoggedAt: <%= user.LastLoggedAt %></li>
    </ul>
<% } %>
```
Here, ```is_admin``` in registered as a helper function in actions/render.go (```isAdmin```), which does the following: 

```
func isAdmin(help plush.HelperContext) bool {
	if help.Value("current_user") != nil {
		return help.Value("current_user").(*models.User).IsAdmin
	}
	return false
}
```

Simple enough.

## It's great... can't wait for v.1.0.0

To wrap this already long post up, GoBuffalo **is great**. However, it is currently v0.12.6, and there are some caveats.

### Context

GoBuffalo is all about the ```buffalo.Context``` type (see [doc](https://gobuffalo.io/en/docs/context)). It wraps Go's context.Context, but is much more than that. It's the heart and soul of the application, it knows everything about the application, binds everything together. It keeps track of the ```*http.Request```, the ```ResponseWriter```, the Session, the Params being passed around, etc, etc.

I don't know if it's really a caveat, more a reminder for myself going forward: learn to know your context.

### All included

I alluded to it at the beginning, when talking about ```nulls.String``` and a few subpackages like ```pop```: Buffalo is all included, but it's a pretty tight ship at this stage, and you can't easily substitute, for instance, another ORM for Pop, although Mark Bates, the creator of Buffalo, has indicated that [he is working in that direction](https://blog.gobuffalo.io/the-road-to-1-0-the-beginnings-34bc5e7603d2). I'm looking forward to it.

### Documentation

GoBuffalo is still young and even though the documentation is good, you sometimes have to search for information on the site itself, in the various github repos for Buffalo and all its subrepos and dependencies, in the code itself. That can be frustrating.
It will probably be better and easier to read and write doc for the framework once the architecture is more settled and the boundary between GoBuffalo itself and the other packages (pop, plush for templating, etc.) is clearer.

### 👍

GoBuffalo is really the web framework I had been looking for in Go. It's great fun to use, it's really powerful and there are a lot of things you can build with this. It gave me a nice architecture to work from, and also lots of tools to work with, from Goth, to DB migrations, mailing, templating, etc.

Now that I'm a bit more comfortable with it, I have to think about a nice, real life project I could use it for. Ping me if you have ideas. But I'm pretty sure that with GoHugo for my static web sites and GoBuffalo for web apps, I'll be doing web things in Go for the foreseeable future.

***

_The code for my mock network is at [https://github.com/nicomo/kumanoio](https://github.com/nicomo/kumanoio). It's not completed by any stretch of the imagination, but time was up for this holiday project, and it's back at the non-dev work tomorrow, so..._

_Also, header image for this post is of the [Kumano Kodo Pilgrimage Trails](https://www.flickr.com/photos/rurinoshima/15126473473) by rurinoshima_
