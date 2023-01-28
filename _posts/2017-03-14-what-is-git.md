---
title: "What is git?"
layout: post
post-image: "https://s3.amazonaws.com/mikechilson-blog-assets/git-photo-52608.jpeg"
description: A utility for source code control
tags:
- Programming
- Utilities
- Git
---

The most used version control system in programming today is Git. Git is an actively maintained open source project originally developed in 2005 by Linus Torvalds, the creator of the Linux operating system kernel. Git has been designed with performance, security, and flexibility in mind. Git is well known for being a standard tool in most programmers toolbox. Git works well on a wide range of operating systems, editors and IDE's. Rather than have only one single place for the full version history of the software as is common in once-popular version control systems like Subversion (also known as SVN), in Git, every developer's working copy of the code is also a repository that can contain the full history of all changes.

Here is a quick overview of git's most basic functions. This is aimed toward those that are new to git, don't use it often, or like me just can't fit any more info in your head. 

**Installing Git**
Git is available on all the major platforms. You can go download it by clicking on [this link](https://git-scm.com/).
 
**Setup local config**
You can specify git configuration settings with the git config command. One of the first things you will want to do is set up your name and email address:

$ git config --global user.name "John Doe" 
$ git config --global user.email "johndoe@example.com"


**Create a new local repository**
To create a new git repository create your project directory, open it in a terminal window and type:

$ git init

 

**Link to online repository**
To connect your repository to a remote server::

$ git remote add origin <server>

 

**Add changed files to local repo**

$ git add -A

 

**Commit changed files to local repo**

$ git commit -m “commit message, changes etc”

 

**Push local repo to on-line repo**

$ git push

Hope this was helpful. These are the basic commands you will use day-to-day. For more information please consult the [git documentation](https://git-scm.com/docs) on the git web site.