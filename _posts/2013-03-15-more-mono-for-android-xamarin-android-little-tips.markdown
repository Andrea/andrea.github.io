---
author: roundcrisis
comments: true
date: 2013-03-15 16:22:57+00:00
layout: post
slug: more-mono-for-android-xamarin-android-little-tips
title: More Mono for android (Xamarin.Android) little tips.
wordpress_id: 1062
categories:
- mobile dev
- mono for android
- UI
tags:
- mono for android
- xamarin for android
---

Mono for android or Xamarin.Android little tips:

 

  
  1. If you turn on GPU emulation, sometimes GPU emulation doesn’t actually start, it downgrades to software rendering, this makes the emulator slower and it doesn’t actually uses OpenGL(if you are using monogame, this means your game would probably not work).
   
  2. If you are looking for a grid like component that stretches with a fix number of grids, I couldn’t find one. Had to write my own and the code is ugly ![Sad smile](http://roundcrisis.files.wordpress.com/2013/03/wlemoticon-sadsmile.png).
   
  3. You can use ScreenOrientation = ScreenOrientation.Portrait as an attribute in your activity and ConfigurationChanges = ConfigChanges.Orientation is also an activity attribute that prevents the activity from restarting when orientation changes.
 

Xamarin just announced support for C# 5 features in the mobiles suites, very exciting news… more details [here](http://blog.xamarin.com/brave-new-async-mobile-world/).

 

Tomorrow, post about [monogame](http://monogame.net) stuff.
