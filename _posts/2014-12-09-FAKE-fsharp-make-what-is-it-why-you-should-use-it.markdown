---
date: 2014-12-09 11:44:00
layout: post
title: FAKE, What is it and Why you should check it out
categories:
- programming 
- development
- Fsharp
- AI
- Conferences
---

I have mentioned FAKE (aka F# Make) in pretty much all the talks I have done so far, however I never explained some of the key aspects of this amazing build DSL.

FAKE is a is a build automation system with capabilities which are similar to make and rake. 
The DSL includes support for: 

  * building with MsBuild + xbuild
  * Testing with nUnit, xunit,  MSpec
  * Creating nuget packages
  * Ziping resulting files
  * [More!](http://fsharp.github.io/FAKE/apidocs/index.html)    
 
### Good to know

* It's mature. I want my build scripts to be reliable and easy to change, if this was a  toy project by someone I would be a little hesitant in recommending, however with over 4 years in development, FAKE is a mature project.
* Builds for .net and mono, it's cross platform. (disclaimer I don't use mono in production so I haven't felt any pain on that) However I some people [do](http://youtu.be/Awl4vGo7Yj0?t=14m52s).
* Builds C# projects too. It might be obvious to some, but FAKE builds C#, VB and F# projects :D.
* No need to know F# to use it. As much as I like F#, some might consider the language a barrier, I have shown to more than one non F# developer FAKE scripts and they understand what is going on. There is a real benefit on having a build system built on a strongly . also check out a really good article called [FAKE Everywhere](http://www.ilker.de/fake-everywhere.html).
* Integrates with CI Server. The integrations I know of are TeamCity, MyGet and Appveyor. We use both [TC](http://fsharp.github.io/FAKE/teamcity.html) and MyGet and they work nicely.  

### When do we use it

From the very beginning we have been using [TeamCity](https://www.jetbrains.com/teamcity/) as our CI server for a long while, however having one click builds is really powerful.

* Debbuging. We have about 20 different solutions contributing to making the game we work on a reality, sometimes, when something go wrong we need to debug certain aspect of the game, as the game runs, the thing is, building and copying the dlls in the correct places can be error prone, we avoid that by building with FAKE and copying to a given path automatically, all with F# and FAKE
* Different targets. x86, x64 builds as well as custom targets (for example we have one for [Steam(the PC games store)](http://store.steampowered.com/app/310850/) 
* Deployment. We have to remove certain content and package the game with just the bits needed to run, this requires some custom removing and adding of things at the right time.

One of our build scripts is open source, I spent a lot of time looking at OSS projects that use FAKE, as it is, in my humble opinion, the best for of documentation: 

* [FsCheck](https://github.com/fsharp/FsCheck/blob/master/build.fsx)
* [OctoKit](https://github.com/octokit/octokit.net/blob/master/build.fsx)

### Summary

Try it, you will probably love it.


### Resources
* [Fake Docs](http://fsharp.github.io/FAKE/gettingstarted.html)
* [FAKE Everywhere](http://www.ilker.de/fake-everywhere.html)
