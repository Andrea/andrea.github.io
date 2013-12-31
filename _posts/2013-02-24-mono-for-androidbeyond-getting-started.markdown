---
author: roundcrisis
comments: true
date: 2013-02-24 12:18:10+00:00
layout: post
slug: mono-for-androidbeyond-getting-started
title: Mono for Android - Beyond getting started
wordpress_id: 1053
categories:
- android
- c#
- mono for android
tags:
- emulator on x86
- Ice Cream sandwich
- mono for android
- xamarin for android
---

A few weeks ago I bit the bullet and bought Mono for Android. I also decided to update to all devices to Ice Cream Sandwich as the UI is just so much better. Should have done that ages ago, but I was just afraid Kies would brick my phone again.

Anyway, the new features that I m sure anyone interested in android development already know about: Services, fragments, new UI. Cool stuff, it also meant a lot to learn ![Open-mouthed smile](http://roundcrisis.files.wordpress.com/2013/02/wlemoticon-openmouthedsmile.png).

Some things that you might want to try out if you are starting this out:

  
  1. Preferably have a device or two ![Winking smile](http://roundcrisis.files.wordpress.com/2013/02/wlemoticon-winkingsmile.png), the emulator is slow. [The x86 emulator](http://docs.xamarin.com/guides/android/deployment%2C_testing%2C_and_metrics/configuring_the_x86_emulator) is an interesting option, it didn’t work for me initially but then I tried a few different virtual devices and then you could really see the benefits… way faster. Still is good to deploy to the phone often enough.  
  2. Since android 3.0 there is a new way to do drag drop that works as a state machine. More info in the excellent [Jeremie Laval’s blog](http://blog.neteril.org/blog/2013/01/28/mfa-tricks-number-8-dragging-around/). Check the other posts, they are really cool too. 
  3. Fragments are trickier to deal with that I thought. Pretty sure I’m doing something wrong (as all times you start learning something new) but I wanted to replace a fragment (with UI elements on it) with another fragment (also with UI elements on it) however if the first fragment was placed there with the layout xml and the second one programmatically, It just didn’t work. It did work when both where placed programmatically. Any hints on this would be great.
  4. To use the [Holo](https://developer.android.com/design/style/themes.html) Theme across your app, simply add this [snipet](https://gist.github.com/Andrea/5023609) to your manifest to your manifest. More on styles [here](https://developer.android.com/guide/topics/ui/themes.html).
 

[![android manifest segment](http://roundcrisis.files.wordpress.com/2013/02/capture.png)](https://gist.github.com/Andrea/5023609)

One to check out… there is an android unit test suite [Andr.unit](https://spouliot.wordpress.com/2011/10/30/andr-unit-joins-the-family/) ([github repo](https://github.com/spouliot/Andr.Unit))a unit testing framework for android based on [Touch.Unit](http://spouliot.wordpress.com/2011/09/28/unit-testing-and-monotouch/).
