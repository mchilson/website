---
title: Create an autorun CD/DVD
layout: post
post-image: "https://s3.amazonaws.com/mikechilson-blog-assets/cd-dvd-disk-floppy-disk-51346.jpeg"
description: How to make any CD/DVD autorun when you load it into the drive.
tags:
- technology
- CD/DVD
- autorun
---

The CD autorun feature is provided by file "autorun.inf" placed in the CD root directory. This is a simple text file so you can use any editor to create it.

The "autorun.inf" file must start with the following line:

[AUTORUN]

It can include the following commands (all commands are optional):

OPEN=exefile

Specifies the command that is to be autorun when the CD is inserted. It may include a path and any arguments. If you do not use this command the root folder of your CD will open automatically. Note: Windows autorun can only open an executable application (*.exe, *.bat) but not a data file (e.g. HTML).

For opening data files the command will be:

OPEN=command /c start datafile

Specifies the name of the icon file that will be used by explorer as the icon for your CD. If you do not use this command the default icon of your CD Drive will be displayed automatically:

ICON=cdicon.ico

Note: You can also specify icon from executable file. This may be the name of an executable file that contains an icon. If the executable contains more than one icon then an optional index field can be specified to indicate which icon to use (beginning from 0):

ICON=exefile,index

So for autorun "cdstart.html" file placed in CD root directory you have to create "autorun.inf" which will look like:

[AUTORUN] OPEN=command /c start myfile.html