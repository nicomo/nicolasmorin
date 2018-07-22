+++
date = "2017-06-18T10:24:53+02:00"
title = "Hugo on Firebase"
description = "How to deploy a gohugo site on firebase"
tags = [ "golang", "gohugo", "firebase" ]
type = "post"
image = "img/hugo-logo.png"
+++

This is a short post to document how I deployed my [Hugo](https://gohugo.io) static website to Google [Firebase](https://firebase.google.com) hosting. I do not cover Hugo itself: see their [Quickstart guide](https://gohugo.io/overview/quickstart/).

You need to install [Node.js](https://nodejs.org/en/download/) first, as it is required by the [Firebase CLI](https://firebase.google.com/docs/cli/), which is then installed from the terminal using: `npm install -g firebase-tools`

You can now connect your local machine to your Firebase account: `firebase login` will open a browser window and ask you, using your Google credentials, to authorize Firebase.

A Firebase project is a directory with a firebase.json file at the root. Firebase tools walk you through the creation of the file. You first have to go to your Hugo website directory on your machine and init the firebase.json file from there. For me that would be:  

````
$ cd Sites/nicolasmorin/
$ firebase init
````

Firebase asks you a few questions as to the Firebase services and setup you want: 

- Which Firebase services do we want. Only one: _Hosting - Configure and deploy Firebase Hosting sites_
- Associate this (local) project directory with a (distant) Firebase project: _create a new project_
- What do you want to use as your public directory? _public_
- Configure as a single-page app (rewrite all urls to /index.html)? _No_

You can now go to the [Firebase console](https://console.firebase.google.com/) and create a project, which basically just asks you for a name, e.g. `nicolasmorin`

Back in the CLI, run 

```
$ firebase use --add
Which project do you want to add? _nicolasmorin-xxxx_ (suggested by the CLI)
What alias do you want to use for this project? (e.g. staging) _prod_
```

Make sure the config.toml at the root of your Hugo site has the base URL for your site: `baseurl = "https://nicolasmorin-xxxx.firebaseapp.com/"`in my case since, for the time being, I have not set up my domain to redirect to the firebase hosting.

You can then generate your site from hugo: `hugo -b https://nicolasmorin-xxxx.firebaseapp.com` will generate all the files, css, etc. required for your site in the /public folder previously created by Firebase.

You can now test your site locally using `firebase serve`. If all looks good, you can `firebase deploy`, which should give you back the URL for the project Console: https://console.firebase.google.com/project/_nicolasmorin-xxxx/overview and for the public site : https://_nicolasmorin-xxxx.firebaseapp.com

If you head over the the Console, in the Domain section you'll see the history of your deploys.

Lastly, you'll want to use your own domain.

From the Firebase console, under Hosting, you can use the Connect Domain button. You'll be asked to specify the domain, and provided with a TXT record to add to your DNS file at your registrar. Your DNS can take a little while to activate, but once Google Firebase has been able to verify that you do own the domain, they'l provide you with the A record for your DNS, pointing to their machines. Update your DNS accordingly. Again this can take a while to propagate, but that's basically it.

One of the nice side effect of using Firebase for hosting here, is that your site is now https by default.

You can now update your Hugo config file to put your actual domain in the baseurl and update your site.

````
hugo -b https://mydomain.com
firebase deploy
````
