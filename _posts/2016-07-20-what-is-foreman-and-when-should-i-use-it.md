---
title: "What is Foreman and when should I use it?"
layout: post
post-image: "https://s3.amazonaws.com/mikechilson-blog-assets/George-Foreman-525485.jpg"
description: An overview of the foreman gem.
tags:
- Ruby
- Gem
- Foreman
---

Many times when writing complex ruby applications or using frameworks (like Rails, Sinatra, or others) you end up having several processes that have to be running during development to allow it to run such as web services, message queues, or some other type of process. Foreman allows you to manage these different processes under one management gem. Foreman uses a file called **Procfile**.

**Getting Started**

First, let's setup the Procfile. A Procfile is a list that contains a name to identify the process and the command used by the system to run it. Foreman will look for it by default in your project's root directory.

Here is an example Procfile of a Ruby on Rails application running Resque workers in the background:

```Ruby
web:bundle exec thin start -p $PORT
worker:bundle exec rake resque:work QUEUE=*
```
Once your Procfile is in place, install the foreman gem:

```Javascript
$ gem install foreman
```

Once the Gem is installed you can start up your application from the command prompt, all you need to do is run foreman start. By default, this will run one instance of the each application type defined in your Procfile.

Foreman also supports concurrency or the ability to run more than 1 process of each type via the concurrency -c parameter. You must define the number of each process type to run.

For example, to increase the number of worker processes to three (3), execute:

```Javascript
$ foreman start -c web=1,worker=2
```
Pretty cool gem eh? There is a lot more to read on the web and Ryan Bates even did a great video about the foreman Gem. Here are a few links to help you become a foreman expert.

[Heroku - Process Types and the Procfile](https://devcenter.heroku.com/articles/procfile)

[Ryan Bates RailsCast video on Foreman](http://railscasts.com/episodes/281-foreman)

[David Dollar - Introducing Foreman](http://blog.daviddollar.org/2011/05/06/introducing-foreman.html)

Foreman is a great tool to help you manage complex process control for your application. Hope you find it useful.