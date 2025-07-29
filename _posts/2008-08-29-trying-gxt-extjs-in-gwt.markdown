---
author: roundcrisis
comments: true
date: 2008-08-29 10:13:00+00:00
layout: single
classes: wide
slug: trying-gxt-extjs-in-gwt
title: Trying GXT (ExtJs in GWT)
wordpress_id: 43
categories:
- GWT
---

Today I'm trying out Ext GWT  
  


  


To use Ext GWT  


  
  
  
  
Installation was simple ( i needed the java sdk i got 1.6Update 7 )  
  
  
downloaded GWT1.5.1 and decompressed it. happy days!  
  
  
then i ran the sample hello and I was running, really fast  
  
  
  
  
  
[if you have problems with some error that ends with  and then an exception, it s very likely to be that your path is reading some other version of java first, if so go to environment variables and change your system settings so you have the recently installed java sdk first]  
  
  
  
  
  
to check the java version open the command line and do java -version  
  
  
**Why Ext GWT?**  
  
  
  
  
  
GWT is a compiler that converts Java source into JavaScript  
  
  
this means you write and test java code  
  
  
  
  
  
  
**Getting Started**  
  
  
as in the sample i went and changed the email application and it changed properly and that was cool, lets get to the business now  
  
  
lets create our own app and try to handle some event  
  
  
  
**Creating an Application**  
  
  
There is an ApplicationCreator that generates a series of files including a java file with a sort of hello world, an html file a css file and two cmd files this all following a naming convention.  
  
  
  
  
  
**Adding support for GWT -EXT**  
  
  
OK I went to the [Ext GWT documentation web](http://extjs.com/helpcenter/topic/com.extjs.gxt.help/html/gettingstarted/gettingstarted.html) and there are a few screencast, if you follow them you get to the EXT-GWT (from extjs.com) hello world however there isnt much more sample applications , there is one but seems like a big jump  
  
  
****  
  
To be honest this took a while to get right, I'm not used to java and the path convention is a bit too strange, i followed the video in the docs above and finally its working :)
