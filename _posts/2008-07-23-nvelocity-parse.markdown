---
author: roundcrisis
comments: true
date: 2008-07-23 20:12:00+00:00
layout: post
slug: nvelocity-parse
title: NVelocity Parse
wordpress_id: 37
categories:
- NVelocity
---

A little thing that drove me completely insane  
  
when using parse ([appache ref](http://velocity.apache.org/engine/releases/velocity-1.5/vtl-reference-guide.html)) the path to the view includes the folder that you are in  
  
say you are in the folder .../views/Blog  
editing a view called one.vm  
if you want to parse something in the same folder as one.vm you have to use  
  
#parse("Blog/two.vm")  
and if you happen to use a / before blog you ll get a nice exception that has a very unclear message  
  
Just to note
