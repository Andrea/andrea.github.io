---
author: roundcrisis
comments: true
date: 2012-08-06 10:05:53+00:00
layout: post
slug: fail-to-add-a-sprite-to-xna-content-project
title: Fail to add a sprite to XNA content project
wordpress_id: 1018
categories:
- gamedev
- xna
tags:
- gamedev XNA sprite Xna-profiles
---

This is not a big one but it’s good to know.

 

I was spiking a little thing in a new XNA 4.0 game project and then attempting to include a _png_ into the content folder, the file was there, I could see it (using show all files menu) but when using the context menu “Include in project” nothing was happening. Why?

 

[![Capture](http://roundcrisis.files.wordpress.com/2012/08/capture_thumb.png)](http://roundcrisis.files.wordpress.com/2012/08/capture.png)

 

First I thought maybe the file type is not supported, but PNGs are. Then someone pointed out, is this a project on a [Reach Profile](http://blogs.msdn.com/b/shawnhar/archive/2010/03/12/reach-vs-hidef.aspx)? textures larger than 2048 are not supported, this was a large sprite-sheet. So, I changed the profile of the project and I was able to Include the file. ![Smile](http://roundcrisis.files.wordpress.com/2012/08/wlemoticon-smile.png)

 

Happy Monday
