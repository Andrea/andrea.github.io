---
author: roundcrisis
comments: true
date: 2009-05-11 10:48:17+00:00
layout: post
slug: gwt-ext-charts
title: GWT-Ext Charts
wordpress_id: 249
categories:
- GWT
tags:
- gwt-ext
---

A quick post about Gwt-Ext Charts.
[](http://www.gwt-ext.com/demo-charts/)

[![](http://www.gwt-ext.com/demo-charts/images/thumbnails/column-chart.gif)](http://www.gwt-ext.com/demo-charts/)Getting charts to work in GWT-Ext can be a little painful.

There is 3 things you have to make sure you have:


## 1 


**<inherits name="com.gwtext.Charts"/>**

in your <YourApp>.gwt.xml


## 2


the **gwtexux.jar** file in your classpath, and of course the jar file should be wherever you are pointing to  ;).


## 3


Most importantly the swf file that is on wherever you set your express install, in the demo is set to
`
chart.setExpressInstall("js/yui/assets/expressinstall.swf");
`
and even tho i had my library where it should, for some reason for me it wasn't uncompromising to the right path so I uncompressed what i needed to _public/js_.

 

**Note:** Sometimes the charts don't actually work on hosted mode, so you should compile/browse and its there ... in Firefox and Chrome but of course it doesn't work on ie :(, this is depending on the version of flash you have.
