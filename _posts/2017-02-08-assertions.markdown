---
author: roundcrisis
comments: true
date: 2017-02-08 10:48:00+00:00
layout: single
classes: wide
slug: Initialization Error on JVM based tests
title: Initialization Error on JVM based tests
categories:
- scalatest
- junit
---

If you are working with intellij and gradle you might at some point hit the 

Initialization error :
"java.lang.AssertionError: Java Assertions should be disabled!"

this is because intellij doesn't import this setting from gradle.

To disable it go to Run -> Edit Configurations... in VM options remove `-ea` 
Removing this option means we are not checking for [assertions](http://docs.oracle.com/javase/specs/jls/se8/html/jls-14.html#jls-14.10) sometimes external libraries use this.


![intellij]({{ site.images }}/2017/settings.png)