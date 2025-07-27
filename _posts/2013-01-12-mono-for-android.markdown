---
author: roundcrisis
comments: true
date: 2013-01-12 13:24:15+00:00
layout: single
classes: wide
slug: mono-for-android
title: Mono for android
wordpress_id: 1043
categories:
- c#
- mono for android
tags:
- mono for android
- permissions
- android
---

I’ve been playing with mono for android the last few days. I have also tried it about 2 years ago. It was a good tool then, and it got much much better.

 

Getting started is pretty simple, you download the ins![](http://blog.xamarin.com/wp-content/uploads/2012/05/android-i86.png)taller, install. It will install all prerequisites for you on your machine. Allegedly this failed the first time but worked the second time, I had a log to look at to give me some idea of the problem.

 

Once I got set up I started reading the documentation. Not only it was in place, but also, it was written to the right level (i.e. assumes you are a smart individual), I then moved on to pricing, 400 usd ouch, but I will come back to this. If you don’t activate the product you can test on the emulator. It gives you some sort of idea of what the experience is like. The emulator is slow, and brittle, but that is something we should talk to Google about.

 

At this point I started going over some tutorials, using both monodevelop and VS just for the fun of it. The main thing I miss from VS when I’m in monodevelop is [resharper](http://www.jetbrains.com/resharper/) ![Sad smile](http://roundcrisis.files.wordpress.com/2013/01/wlemoticon-sadsmile.png). I had no real troubles getting on with creating a little app (a games reviews collector) .

 

I went ahead and bought the license, activated and pushed to the device and it is much faster than using the emulator.

 

One gotcha was that I wanted to write files and then be able to access them via USB, I kept getting a file permission error, I needed to set up the permission on the manifest file, it wasn’t obvious to me, but that is ok. All the information I needed was [here](http://docs.xamarin.com/Android/Guides/Advanced_Topics/Working_with_AndroidManifest.xml).

 

Deployment to other devices is also pretty simple, you build the app on release mode and use the *-Signed.apk, there are other ways to deploy [here](http://docs.xamarin.com/Android/Guides/Deployment%2C_Testing%2C_and_Metrics/publishing_an_application). 

 

Mostly the reason for this blog post is that I was a bit surprised with how good an experience it was (so far) .

 

Next I will be working with some eventually connected storage, I heard good things about [Parse](https://www.parse.com/). 

 

I gave myself a pomodoro to finish this post, so I’ll have to talk about pricing in tools some other time ![Smile](http://roundcrisis.files.wordpress.com/2013/01/wlemoticon-smile.png).

 

Till the next time
