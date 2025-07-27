---
author: roundcrisis
comments: true
date: 2012-12-27 14:45:06+00:00
layout: single
classes: wide
slug: directory-truncator
title: Directory Truncator
wordpress_id: 1039
categories:
- OSS
tags:
- open source directory
---

Recently I needed some code to truncate a directory of files or folders, for example I wanted to remove files or directories given a max number of files or directories. [![Polyhedral 'foam' by truncated octahedra](http://upload.wikimedia.org/wikipedia/commons/9/93/Truncated_octahedra.jpg)](http://en.wikipedia.org/wiki/Weaire%E2%80%93Phelan_structure)This is a common task when you have backups and you don’t want every single backup since forever, but you want to keep the last 5 ones. Another common scenario is when you have builds and you only probably want the last 10 (particularly if your build is used only by 4 people that seat across from you).

 

Anyhow, I have written similar code in the past and I know I will probably need something that does the same thing in the future, so I created a super small library and I put it on [github](https://github.com/Andrea/DirectoryTruncator). 

 

I think the tests explain better what the code does than I do. So have a [look](https://github.com/Andrea/DirectoryTruncator/blob/master/DirectoryTruncator.Tests/DirectoryTruncatorTests.cs).

 

There are a few things that I want to add to this project

 

  
  1. Logging and or console output so you know what happened, I couldnt so far decide on what is the best approach or if I want to choose one, so I ll do that tomorrow .
   
  2. On error, proceed to the next file/folder.
   
  3. Have a StartsWith parameter(on both methods), so that it only deletes files or directory that start with 
   
  4. Turn it into a service
 

There are probably more things that could be done with it, but honestly, that is all **I** need.

 

Comments, questions or any feedback welcome!

 

Note: The image above is totally unrelated but I found it looking for truncated. What I found interesting about it is that the article this image relates to is about the Wearie-Phelan structure, this structure inspired the Beijing National Aquatics Centre and other cool stuff you can read [here](http://en.wikipedia.org/wiki/Weaire%E2%80%93Phelan_structure).

 

Happy holidays
