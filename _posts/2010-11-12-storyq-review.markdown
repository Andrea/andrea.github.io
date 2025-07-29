---
author: roundcrisis
comments: true
date: 2010-11-12 15:02:09+00:00
layout: single
classes: wide
slug: storyq-review
title: StoryQ Review
wordpress_id: 724
categories:
- bdd
- unit-testing
tags:
- StoryQ
---

We are evaluating BDD frameworks at the moment and I'm going through [StoryQ](http://storyq.codeplex.com/).

Note:



	
  * Internal DSL for BDD, for me this means I can discover a lot by just following the API (ie its got a nice fluent API)

	
  * The Code for adding a story is very simple (example below)

	
  * Readable and nicely formatted report output

	
  * Supports Nunit, xUnit and MSTests

	
  * if using xUNit there is no support for incomplete tests ( ie if you are using CI it will break the build) UPDATE: there is a way since xUnit 1.7

	
  * Also you need to override the settings with your own exception builder.

	
  * I had one of those Doh! moments because I setup the story and the scenario with the Given().When().Then() and then I called the Execute method, that was not going to work… :(

	
  * Can report in various format, the report shows up on resharper or in an more html way.

	
  * There is a wpf app that converts gherkin and it generates the StoryQ test.( couldn’t try because the app failed, I think it s because of a dodgy build I have but will find out and report later)

	
  * Seems to support well the idea of many scenarios per story within the same file, which is cool.

	
  * Good to keep in mind not to use underscores in method names [Link](http://storyq.codeplex.com/Thread/View.aspx?ThreadId=218277)


So far so good, if there is anything else noteworthy I ll update.

[![sq](http://roundcrisis.files.wordpress.com/2010/11/sq_thumb.png)](http://roundcrisis.files.wordpress.com/2010/11/sq.png)
