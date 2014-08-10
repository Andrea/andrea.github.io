---
date: 2014-08-10 14:13:00
layout: post
title: Build tools FTW
categories:
- programming 
- development
- FAKE
---


At the moment, and for the last while, I have been working on an awesome game [OniKira: Demon Killer](www.digitalfurnacegames.com) (yes we [renamed it](http://www.digitalfurnacegames.com/changing-the-name-of-the-game-figuratively-and-literaly/) recently) from the start we wanted to have a one click deploy, and I believe in walking skeletons..., so, I have been working on having a one click build since the beginning of the project and as we are getting closer to a Steam Early Access for the game and need to send different types of builds to different parties this is really starting to pay off.


## Current Tools

This is a list of tools we are using for the build:

* TeamCity: for building, running tests, etc. I love this tool, like most of [jetbrains](www.jetbrains.com) tools I used over the years. I am curious about their new offering [UpSource](http://blog.jetbrains.com/blog/2013/09/18/upsource-a-platform/) .One suggestion: I wish it would be for the UI would be turned into some script so this could be into a repo rather than a database (I am sure there are good reasons for this but this is what I want right? :D) 
* ScriptCS: There are some custom moving of assemblies depending on target platform, packing of textures, and other crazy stuff with ScriptCS I have little friction and I can script fast in a language I know well (kudos to [Glenn Block](http://twitter.com/gblock), [Justin Rusbatch](http://twitter.com/jrusbatch) and [Filip Wojcieszyn](http://twitter.com/filip_woj))
* BitTorrentSync: Build distribution peer to peer. We are a small however diverse team (ie not all of us that need to have access to the build are developers) this is a pretty efficient and cost effective way to do that. We also use this when editing video or other large binaries.
* MyGet: A lot of the code we write is open source, we pack it and ship assemblies using NuGet via [MyGet](http://www.myget.org). Their response time is amazing (I had a problem once and they responded and fixed a problem in less than 30 minutes, note: I created the problem in the first place ).We have started migrating some of the builds to their build service.
* git: for all code repositories. 
* svn: Content repository (images, sounds, binaries)

## Tools on Testing Phase

Recently I added [#FAKE](http://fsharp.github.io/FAKE/) to our Duality(game engine) build, I was able to do something a custom with the build in a couple of hours (generally custom in build tools is a pain), and it has TeamCity integration so this is something I might use on the next build task I have.

### Thank you 

All of these tools are free (at least the way we use them to build  and many of them are open source. Thanks to all of you that make this possible.