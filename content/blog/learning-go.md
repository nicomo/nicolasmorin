+++
date = "2016-08-15T11:04:51+02:00"
title = "Learning Go"
description = "This is just another “Learning Go” Post"
tags = [ "golang", "programming" ]
type = "post"
+++

*TL;DR: It’s a great language, a good choice to learn programming in general; there’s great documentation available, and it’s detailed. But in part because the Go community doesn’t view frameworks favorably, it can be hard to move from grasping the details to working on a fully fledged project.*

I’m not a programmer, i.e. I have not had any kind of formal training in Computer Science; nor do I work as a developer. But I have worked with programmers quite a lot and, from time to time, I have done some development myself, modest things, simple web sites, manipulating XML documents, working with databases. Things that were mostly prototypes and side projects, and were never meant to be used by a lot of people.

Last April, I decided to be more serious about programming and I started learning Go. I estimate I spent about 10 to 15 hours a week on it from April to July, so that would be something like 200 hours total: it’s still early days, but I thought it might be interesting to jot down my first impressions.

## Golang is crystal clear

There’s a number of blog posts out there already about learning go and the many advantages of the language. See just 2 examples: #golang: The Next Great Teaching Language or Graduating to Go. So I won’t be adding much here.

To me the main advantage of Golang so far can be summed up in 2 words, it’s crystal clear. Specifically:

- The list of keywords is short and the syntax minimal. The simplest example is the use of *for* to also manage *while* loops: `for sum < 1000 { does the trick }`
- Static typing. I love static typing and the compiler. I always struggled with the number of implicit things happening in javascript, for instance, and thus love how Golang gives you a fair amount of certainty about what you’re dealing with, and how the compiler helps you understand and debug your code. I don’t mind a few extra lines of code, as I always thought that brevity shouldn’t be confused with clarity: a lot of really tight code can be fairly obtuse.
Formatting and documentation are great. The Go community seems to put a lot of emphasis on:
  * code that is well formatted: the gofmt command formats your code with tabs, etc., but also tidies your code, rewriting the slice expression `s[a:len(s)]` as `s[a:]`, that sort of thing. Also the compiler won’t allow you to have imports of libraries that are not used and generally helps you keep your code clean.
  * code that is well documented: Godoc outputs documentation for your program, and expects you to comment packages, functions, etc.
  * and the documentation of the language itself is very good: see https://golang.org/doc/
As a trained librarian, I say: documentation ++.
- The standard library is extensive, and you can go quite far before you’d need a lot of third-party libraries: for instance, HTTP client and server implementations and a templating system are both part of the language itself. Also, even though you’d need a third-party DB driver to work with, say, MySQL, that driver itself would use the standard database/sql and database/sql/driver packages. I feel it makes things clearer and simpler.

Concurrency management is also often mentioned as a strong point of Go, but to be honest as a beginner I don’t really have much use for concurrency: I certainly don’t work “at scale” and so far I have not needed goroutines or channels.

## Ongoing struggles

The Go community doesn’t seem to value frameworks much. There are Go frameworks to be sure (Beego, Revel, etc…), but they are fairly new and, judging by the programs of go conferences, the chatter online about Go, etc., they are not talked about very much, nor do they benefit from a lot of enthusiasm from the community, which seems to value minimalism more, tends to turn to lightweight tools such as the Gorilla web toolkit, and favors a more DIY approach.

In a useful 2014 blog post, Nicolas Merouze explained it thus:

> There has been a recent debate on using frameworks vs using libraries. I’m not against frameworks but I think Go has great small packages that we can make a framework of our own pretty easily. If you use Go on long-term projects, I think it is a wiser choice to do it yourself. If you want to learn Go, it is also better to understand how everything works.
For the beginner, the problem becomes: how do you make the leap from understanding the language itself — the use of structs, the Reflect package, etc. — and the most common libraries, like gorilla mux — how do you move from that to making a webapp? How do I move from a detailed, focused view to the big picture: how to structure your application when there’s no framework to do it for you?

Ben Johnson puts it succinctly in a blog post:

> For me, the hardest part of learning Go was in structuring my application. Prior to Go, I was working on a Rails application and Rails makes you structure your application in a certain way. “Convention over configuration” is their motto. But Go doesn’t prescribe any particular project layout or application structure and Go’s conventions are mostly stylistic.

Then he proceeds to show us 4 patterns that he finds useful in structuring his applications. And indeed they are, but it’s not the same thing as taking the beginner by the hand and giving her an overview of how to structure her application.

The closest I’ve seen to that step-by-step tutorial about structuring go webapps is Joseph Spurrier’s Go Web App Example — Entry Point, File Structure, Models, and Routes. It’s from Jan. 2016 and the corresponding github code has more than 300 stars, so there’s no question it resonated with people. He went on to propose Blueprint, a model-view-controller (MVC) style web skeleton in Go. I feel that’s exactly the type of project and documentation that are needed to help the beginner take the next steps from basics to projects. And when I say beginner, I mean “beginner in any language”, for the tutorials and blog posts, etc., about Go very often work on the premise that you’re switching from another language. But a different type of documentation is needed for people who, like me, might have dabbled in various languages, but only start to take programming seriously using Go: it’s one thing to explain how closures work in Go, and another to explain closures using Go; it’s one thing to explain a useful pattern, and another to explain the architecture of an MVC app using Go.

To borrow from Ben Johnson again, I perfectly understand that Go doesn’t prescribe any particular application structure, but at this stage of my learning curve, I think that a set of best practices and conventions going beyond just style would certainly be helpful. Ben Johnson followed up his initial post with another one recently that looks into that: Standard Package Layout

Meanwhile after 3 weeks off this summer, I’m back at my desk and will continue to dedicate 10 to 15 hours a week to Golang during the next year. Maybe I’ll try to revisit this post next summer.

If anyone wants to get going with Golang, here are the resources I’ve found most useful:

- documentation on the [Golang website](https://golang.org/doc/)
- Alan Donovan and Brian Kernighan’s [The Go Programming Language](http://a.co/c7ysfCV)
- go trainer William Kennedy’s blog posts at https://www.goinggo.net/ and his [Go in Action](http://a.co/0Ppme41) book
- the [Go track](http://exercism.io/languages/go/about) at exercism.io