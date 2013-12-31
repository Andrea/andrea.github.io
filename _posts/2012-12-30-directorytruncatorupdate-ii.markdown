---
author: roundcrisis
comments: true
date: 2012-12-30 22:33:03+00:00
layout: post
slug: directorytruncatorupdate-ii
title: DirectoryTruncator - Update II
wordpress_id: 1040
---

So, after the last post, where I [introduced Directory truncator](http://roundcrisis.com/2012/12/27/directory-truncator/), I present you some extra work I have just committed. My plans for it from the previous post where

 

  
  1. Logging and or console output so you know what happened, I couldn't so far decide on what is the best approach or if I want to choose one, so I ll do that tomorrow . 
   
  2. On error, proceed to the next file/folder. 
   
  3. Have a StartsWith parameter(on both methods), so that it only deletes files or directory that start with 
   
  4. Turn it into a service
 

So, this is what happened,

 

  
  1. After thinking a little bit about it, I just went for NLog, it does what I need it to do for the moment. Logs need no test, so I added a few log messages, there is probably some log messages missing. 
   
  2. For this one, I ended up making a decision I’m still mulling over. I needed to test that if there is an error on file delete, the process will log and keep going. How to do that? well, I created a thin wrapper around the file system, as far as I could see it, there was no other way to simulate the scenario of you have two files to delete and one of them is deleted before we get to it. I have yet to do this for TruncateByDirectory.
 

This is all for today, and since this is probably the last post of the year. [Merry New Year!!!][merry]

 
[merry]:[http://www.youtube.com/watch?v=JOiN5TQhP2Q&w=448&h=252&hd=1]

