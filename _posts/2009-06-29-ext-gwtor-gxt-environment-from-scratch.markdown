---
author: roundcrisis
comments: true
date: 2009-06-29 09:26:43+00:00
layout: post
slug: ext-gwtor-gxt-environment-from-scratch
title: 'Ext-GWT(or GXT) Environment from scratch '
wordpress_id: 309
categories:
- GWT
tags:
- GWT
- GXT
---

So... I had to set up a GXT development environment for myself from scratch, so I thought I d share the experience.


## Getting the JDK was painfull


I ll spare you the rant, however I will say that Sun requires that you are registered to download the JDK, after a email like the one below:
`
We're sorry but your Sun Online Account password could not be reset.`

` `

`We would be happy to look into this further for you.  Please forward this email to us at login@sun.com.  We apologize for any inconvenience.
`

a 404 ( see screenshot) and a failed attempt to re- register, I ended up getting the JDK from another machine, via remote desktop.

404

![Sun website login 404](http://roundcrisis.files.wordpress.com/2009/06/sun404.jpg?w=300)

**JDK**, check


## Ant


Next thing on the list was to get **ant**, I went to the appropriate [website](http://ant.apache.org/bindownload.cgi) got the binaries, un-zipped, set the ANT_HOME, and proceeded to add ant to my path, checked that the version was the correct one with

`
ant -version`
and all fine

**ant** : check


## Installing GWT


Then i went to get GWT , downloaded, unzipped, added the GWT_HOME (not required but handy) then ran the mail sample in hosted mode as described in the [GWT documentation getting started](http://code.google.com/webtoolkit/gettingstarted.html#Install) win **ant deploy**


## **Creating a project with GWT 1.6.4**


A lot has changed since version 1.5.3 the two more obvious things so far are: speed running the hosted mode, the layout of the project files, and the application creatorand now you have to use **webAppCreator.cmd** (extension depends on your platform of course) , then, since I use eclipse I can jsut import the project and start working with it, tho I wanted to try [GXT](http://extjs.com/products/gxt/) .


## **Installing and using Ext-GWT (or GXT) 2.0 RC1**


GXT 2.0 required GWT 1.6.x ( I m using 1.6.4) , at a glance, there are a lot of things that make GXT look really good, like active development and a roadmap :D, some new widgets, support plans, etc.

There are a few steps required to make GXT work in the project I created in the previous step,



	
  * Copy the **Resources** folder into the project **war** folder (you could call it something else but I dont see the point yet), then, as described in the setup.txt,

	
  * Add the stylesheet to the host page html

	
  * Add the <inherits ..> to the ..Gwt.xml,

	
  * Include the gxt library to the project classpath

	
  * and include to the Launch configuration.


To check that this is a GXT app we write a bit of code on **onModuleLoad** method:

Button button = new Button("Click here");

ContentPanel panel = new ContentPanel();

panel.setTitle("GXT Test");

panel.setHeight(400);

panel.add(button);

RootPanel.get().add(panel);


gets me something like:




![gxt](http://roundcrisis.files.wordpress.com/2009/06/gxt.jpg?w=300)




Task Completed. Next task, get a basic layout with a grid populated by JSON.




Button button = new Button("Click here");




ContentPanel panel = new ContentPanel();




panel.setTitle("GXT Test");




panel.setHeight(400);




panel.add(button);






RootPanel.get().add(panel);
