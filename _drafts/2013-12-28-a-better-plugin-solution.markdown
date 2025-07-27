---
layout: single
classes: wide
title:  "A better plugin solution, trying out Roslyn and MEF"
date:   2013-12-28 21:40:10
categories: c# Roslyn 
---

Difficulty in this plugin system is that the plugins need to be hot-swaped, with minimum disruption to the rhost application.
The initial possible solution is to work with multiple AppDomains.


## Objective

That I can reload a component when it changes from a host application. Research for scripting options and how hard it would be to use Roslyn for it.



## Roslyn

I started having by a look at Roslyn. And what it could do for us. 

I found this post to be a [great intro to Roslyn][3] 
More [useful links to learn and understand Roslyn][bitly-bundle] 

A smart person once said "If you can't explain it to a six year old, you don't understand it yourself." so I'll try.


Roslyn is a compiler as a service that allows you to create or delete any section of a syntax tree. 

- After some tests about re-compiling code and building assemblies I realized that Roslyn, is really cool, but it wouldn't really do exactly what I was looking for. This mini research allowed to understand what Roslyn is capable of tho. I also had a look at [ScriptCS][script-cs] (really want to have another look at this), and also [CS Script][cs-script] I didn't hear about this before.
I think some of this goodness needs to get into Dualitor, as soon as we need it.

[How to load a dll created by Roslyn in C#][1]

[Advantages of ScriptCs over Roslyn][2]

## MEF
- So I moved on to MEF. When MEF came out a few years ago, I never had the chance to look at it properly.
	Some Resources:
	*  Great [overview of MEF][4] 

## AppDomains and shadow copying

- Shadow copying is a technique to avoid the locking of assemblies. A problem with this is that it appears 




[1]:http://stackoverflow.com/questions/10751079/loading-an-assembly-generated-by-the-roslyn-compiler

[2]:http://stackoverflow.com/questions/18406109/scriptcs-hosting-advantages-over-roslyn

[3]:http://msdn.microsoft.com/en-us/vstudio/hh500769#Toc306015672

[4]:http://mef.codeplex.com/wikipage?title=Overview

[bitly-bundle]:http://bitly.com/bundles/roundcrisis/4
[cs-script]:http://www.csscript.net/
[script-cs]:https://github.com/scriptcs
