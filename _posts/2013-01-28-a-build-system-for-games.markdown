---
author: roundcrisis
comments: true
date: 2013-01-28 23:22:02+00:00
layout: single
classes: wide
slug: a-build-system-for-games
title: A build system for games
wordpress_id: 1046
categories:
- c#
- gamedev
- unit-testing
- xna
tags:
- build server
- gamedev
- monogame
- teamcity
- xna
---

As you might or might not know, I am one of the founders of BatCat Games, the important word about that sentence is **games. **The fact that we make games put a series of differences into our production that doesn’t generally affect non game software development cycles.

For a start art and animation are key in a game, so are visual effects. In build server terms, that generally means two things: It requires space(for content building) and quite probably a graphics card (for the visual effects). Our ideal solution would be to have a virtual machine per supported platform , but we found that none of the virtualization software (VirtualBox, VMWare, etc) virtualizes the graphics card reliably (if you found a way, please let me know)  so we are running our server on a non virtual machine.

The objective is to build the whole game, tools, etc. at each commit. There are a series of tools available in the market at the moment that allows you to do just that. For example: TeamCity, Jenkins, CruiseControl, Hudson.. etc. There is a good comparison matrix [here](http://confluence.public.thoughtworks.org/display/CC/CI+Feature+Matrix).

We chose [TeamCity](http://www.jetbrains.com/teamcity/), mostly because we know it, we find it easy to use and it is free.


### Our setup


Our code is based around XNA and [monoGame](http://monogame.net/) (recently on version 3).

We have many projects: a game and engine project, a tool, a library and the content builder. This means we have a diverse project output. For example, in the case of the content, we are not interested in the actual build results (yet) however we are interested in knowing that it did build, and to report errors if it didn’t.

The game and engine project reside in one solution and have many unit tests. We need the build server to not only build the project and after that run the unit and integration tests. Initially I set this up using [psake](https://github.com/psake/psake) (a tool that does the build with PowerShell) this is a great solution if you want to have a one click build, so I gave it a try, I found that setting up the tests assemblies was a manual process and that to get psake to talk to TeamCity nicely it would take more time that I had. So I tried running the build directly from TeamCity, and it was easier and I didn’t loose to much flexibility so, I had to go for that solution (however is a decision I will revisit shortly).

[![Capture](http://roundcrisis.files.wordpress.com/2013/01/capture_thumb.png)](http://roundcrisis.files.wordpress.com/2013/01/capture.png)

Setting up each of the steps took me approximately 10~20 minutes if done this way. There are a few things that I want to improve on, however the end result is that in a very short time I can have a new project building and reporting.

Some of the disadvantages of the process as it is are:



	
  1. If I want to change the build type I need to do it manually, in this case, the target test assemblies will need to be updated

	
  2. At the moment we are using dropbox as our way to distribute the builds, it is a process some members of our team really like because they just get the new binaries and they can choose when to update (so that there is no friction). I would prefer if the tools would just auto-update, but this is working for the moment.




### Summary


As you can see the server setup is not perfect, there is loads to improve on, but setting this up from early on has proven very helpful. It allows us to have a one click build and a functional way to deliver our tools and product to the people in our team.

Note: This post was cross posted to [gamasutra](http://www.gamasutra.com/blogs/AndreaMagnorsky/20130129/185631/A_build_system_for_games.php), Thanks to [Kris ](http://www.twitter.com/KrisLigman) for her help.
