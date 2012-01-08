---
layout: post
title: "Moving from Wordpress"
date: 2012-01-08 12:03
comments: true
categories: [Wordpress, Octopress, Pow, Github, Heroku]
published: true
---

Well, I've done it!  I've taken the plunge to move my blog from Wordpress.  As any good software developer
will tell you, it's more fun to create stuff than to use something out of the box, so after looking around at
my options, I decided to use Octopress.
<!-- More -->

### What is Octopress
[Octopress](http://www.octopress.org) is basically Jekyll on steroids.  To get started with Jekyll, you have to write your own HTML
templates, CSS, Javascript and set up your configuration.  I was okay with most of that, but I suck at
design.  I love clean crip design, but for some reason, I'm missing that designer skill.  So, since Octopress
does that for me, I was in love!

Other cool things about Octopress is that it uses HTML5.  It also has built in 3rd party support for Twitter,
Github, Google Plus, Disqus, Pinboard and Delicious, to name a few. It also has a ton of plugins.  Some come
from the Jekyll community, but others are specifically made for Octopress.  Oh, and did I mention it's open
source?!

## Getting Started
Getting a new blog set up is a piece of cake.  All you have to do is fork or clone the Github [repo](https://github.com/imathis/octopress).
Next, you have to set up your deployment.  They make it easy to deploy using Github pages or to Heroku.  I
decided on deploying to heroku.  I like the fact that I can keep my source on Github and then push directly to Heroku.
Octopress's documentation makes this so easy for you.

## Add Some Content
Adding a new post is as simple as running a rake task.  It creates a simple markdown file for you that you can edit
in any editor you wish.  I use VIM since I'm pretty familiar with it.  Those that use VIM daily will tell you that
it's difficult to go back to anything else.  Now you've got all of that VIM hotness available to you to while blogging.
It definitely beats that Wordpress template thingy that is hard to use.

As I'm writing, I take a peek at what my post looks like online.  I set up [POW](http://pow.cx) to host my blog locally.
I run a rake task that watches my source and as I save my buffer in VIM, I can instantly see what my post looks like in
the browser.  I've never used POW before, but will use it for everything going forward, especially as I have many projects
set up on my machine and sometimes want to run multiple Rack applications.

## What's Next
I've already learned so much by moving my blog to Octopress.  I get to host my source up on Github, deploy to Heroku,
use VIM for everything, set up POW for my Rack server, and hack on an open source Ruby project.  Next, on my list of
things to do is to make my blog look a little nicer and change from the default template.  I'm hoping since blogging
is now a little bit of coding, I'll do it more.  Look forward to many more posts from me in the future - and if not,
be sure to call me out on it!

