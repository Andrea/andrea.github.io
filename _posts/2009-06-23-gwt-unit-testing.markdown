---
author: roundcrisis
comments: true
date: 2009-06-23 11:12:13+00:00
layout: post
slug: gwt-unit-testing
title: GWT Unit Testing
wordpress_id: 299
categories:
- GWT
tags:
- GWT
- gwt-ext
- unit-testing
---

After some time messing with GWT-Ext

I found a few problems on this front:

- running the test takes too long ( I m writting this post as I wait for the tests to run) , for example to run a test like the one below, takes 10 seconds, and that is after you ran the whole suite, a suite with 23 tests takes aproximately 100 seconds... not great tbh.
`
Dog dog= new Dog();
int legs= dog.legs.length;
assertEquals(4, legs);
int eyes=dog.eyes.length;
assertEquals(2, eyes);
`
- A convention that i dont particularly like ( perhaps because I m not familiar with it) is that the test methods must start with **test, ** ok , on the plus side you dont have any attributes lurking around.

**- **Then there is the obvious problem:  you can really only test certain code, ie things like parsing , etc is all grand, however when it comes to testing that certain controls are there , it becomes very cumbersome.

However, i rather have some unit testing than none.

If you have any experience testing GWT-Ext I would really love to hear about it.
