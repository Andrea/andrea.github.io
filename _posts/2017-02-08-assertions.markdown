---
author: roundcrisis
comments: true
date: 2017-02-08 10:48:00+00:00
layout: post
slug: Initialization Error on JVM based tests
title: Initialization Error on JVM based tests
categories:
- scalatest
- junit
---

If you are working with intellij and gradle you might at some point hit the 

Initialization error :
"java.lang.AssertionError: Java Assertions should be disabled!"

this is becasue intellij doesn't import this setting from gradle.

To disable it go to Run -> Edit Configurations... in VM options remove `-ea` 
