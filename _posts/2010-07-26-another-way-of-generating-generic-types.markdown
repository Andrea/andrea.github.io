---
author: roundcrisis
comments: true
date: 2010-07-26 19:39:15+00:00
layout: post
slug: another-way-of-generating-generic-types
title: Another way of generating generic types
wordpress_id: 633
tags:
- c#
- generics
---

Kick post on Types, nothing outrageous, but this was just a construct that I never used too much.

The other day a collegue and we got stuck on a method similar to this


> void DoStuff(Type **type**)
{
var iInterface = typeof(ISomethingAmazing);
Type genericType = //how to get ISomethingAmazing<**type**>

//do more things
}


and well I didn't know but you can do this


> void DoStuff(Type **type**)
{
var iInterface = typeof(ISomethingAmazing);
Type genericType = iInterface.MakeGenericType(new Type[] { **type **});

//do more things
}


Why would you want this?
well say for example, you are working with a container and need to get all the ISomethingAmazing of whatever your type is
Particularly handy if you are using a handlers or factories a lot.

What happened?

Basically we just had information about the types we wanted but at compile type we didnt know the types, this is a away to return a runtime type even when you dont know what that type is.

I hope this is helpful for someone

Cheers
