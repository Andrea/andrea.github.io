---
author: roundcrisis
comments: true
date: 2010-07-13 22:33:22+00:00
layout: single
classes: wide
slug: when-could-not-load-file-or-assembly
title: When  "Could not load file or assembly" happens
wordpress_id: 613
tags:
- fuslogw
- moq
---

So I was getting an " Could not Load File or Assembly" error, even thou I was pretty certain I was referencing the right dlls in the correct folders. What could this error possibly mean?




The actual error I had was:




> 

> 
> System.IO.FileLoadException: Could not load file or assembly 'Moq, Version=2.6.1014.1, Culture=neutral, PublicKeyToken=69f491c39445e920' or one of its dependencies.




Some things I checked:








	
  * Maybe  I dont have the moq.dll assembly, but it was there.

	
  * Then I checked  the assembly version, my moq.dll was 4.x (the error stated 2.6.x was required), so there is a difference in the expected versions, why?

	
  * Checked all projects in the solution, all the ones using Moq.dll where explicitly pointing at 4.x

	
  * [Reflector](http://www.red-gate.com/products/reflector/) show time. I was using moq.contrib.dll on the project that was failing, and since it makes sense that such library would depend on moq, it was worth checking it out, this is what I saw






[caption id="attachment_616" align="aligncenter" width="242" caption="Reflector Screenshot"][![](http://roundcrisis.files.wordpress.com/2010/07/capture.png?w=242)](http://roundcrisis.files.wordpress.com/2010/07/capture.png)[/caption]



This means that moq.contrib.dll did indeed depend on moq, so I just needed to find a version of it that pointed to the right assembly, I was lucky because I had a set of dlls that work, if you are not so lucky, get latest from the [moq.contrib google code](http://code.google.com/p/moq-contrib/) and simply run the Build.cmd and you are all set to go (you can replace the moq.dll dependecy if they have moved on).




On the way I found some other interesting things








	
  * Like [this](http://social.msdn.microsoft.com/Forums/en/clr/thread/63fe67b6-c3f9-4ae1-b787-b57418326f80) thread, basically it said that this was possibly a compiler bug. I thought damn a dead end, but it wasn't :).

	
  * A tool to find out how the dll binding happen callled **FusLogw.exe**







**FusLogw.exe**




Also known as the Assembly Binder Log Viewer, awesome right? :D




Where is it?  I searched online and the tool seems to move a lot in differnt versions of Windows, In xp




it could be here: **C:\Program Files\Microsoft SDKs\Windows\v6.0A\bin\fuslogvw.exe**




In my windows 7 install I found it here: ** C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0A\bin>FUSLOGVW.exe**




Oh yeah and you need to run it from the command line as an Administrator




It might seem obvious, but you need to refresh after you run something that fails , it is, after all a log viewer
