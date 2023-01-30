---
title: "Favorite Development Gems Part 1 - Rails-ERD"
layout: post
post-image: "https://mikechilson-blog-assets.s3.amazonaws.com/gems.jpeg"
description: Neural Nets in Ruby.
tags:
- Ruby
- Rails
- GEM File
---

This is the first in a series of blog posts on development gems for Rails. I am assuming you know what gems are and their value in the Ruby/Rails ecosystem. If you don't, then [here is a link](https://guides.rubygems.org/rubygems-basics/) to go check out. 

Development gems are used during the development process only and not in production environments. The gems mentioned in this and in the next few posts are my favorites and really help get the work done when developing rails application. Let's get started.

This first post I will be focusing on the **Rails-ERD** gem. 

![sample erd](https://mikechilson-blog-assets.s3.amazonaws.com/gemcutter.png "Logo Title Text 1")

This gem was created by Rolf Timmermans and its primary purpose is to build an Entity-Relationship Diagram for your Rails project that uses the Active Record ORM. It shows a graphical relationship model of all your AR relationships. This is a VERY handy gem to install in the "development" gem group of your Gemfile as it will generate an entity-relationship diagram for your project in the form of a PDF file a will drop it in the root of your project folder. 

Now that you know what the gem does, let's install and use it!

Rails-ERD generates diagrams using Graphviz, a visualization library. This must be installed first. For Linux (Ubuntu and Debian) users here is the command to use:

`sudo apt-get install graphviz`

For other platforms, please consult the installation guide [here](https://voormedia.github.io/rails-erd/install.html).

Next, let's go to [rubygems.org and look up the Rails-ERD gem](https://rubygems.org/gems/rails-erd) to copy the text to add to our project's GemFile. For example:

`gem 'rails-erd', '~> 1.6'`

After saving your GemFile be sure and run bundle install to install the gem locally for your project. Now we are ready to use the gem.

For rails 5.x  and later, at the terminal prompt in your project folder issue the command:

`rails erd'

You will now see a .pdf file generated in the root of your project folder. This is the entity diagram. 

One command with this gem produced an Entity-Relationship Model for your Active Record objects so go give it a try!

**Rails-ERD Resources**
Site: [https://voormedia.github.io/rails-erd/](https://voormedia.github.io/rails-erd/) github: [https://github.com/voormedia/rails-erd](https://github.com/voormedia/rails-erd)

