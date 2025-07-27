---
author: roundcrisis
comments: true
date: 2011-07-09 11:49:46+00:00
layout: single
classes: wide
slug: tdd-tools-for-net-developers
title: TDD tools for net developers
wordpress_id: 828
---

In the last few years the tooling available to .net developers for unit testing in general has matured, these are some of the tools  that I either used or heard of :

Continuous Integration:



	
  * Team City: I use it and really like it, simple to set up and use, if you want to try it they have a free professional edition .

	
  * Cruise Control.net: Open source, used it but didnt find it too friendly, I m aware a lot of people use it

	
  * Hudson. Originally a Java only project but there are some success stories on the .net fence, has some features unavailable in the other two mentioned above.

	
  * there must be something else. ?




BDD Frameworks








	
  * StoryQ:  This is what I use. Like it because you write C# code with some constraints and it generates reports on the behaviour. Samples: [code](http://storyq.codeplex.com/SourceControl/changeset/view/2d36d2927f4d#src%2fStoryQ.Demo%2fDemoTest.cs) [report](http://yfrog.com/h2y3mtp)

	
  * Cukes/Cucumber: I remember the first time I saw cucumber in action I was really impressed, however it's hard to get buy in for a tool that requires another language installed, probably fine for some projects, it depends a lot on the project, the company and the culture.

	
  * SpecFlow:  you write features in Gherkin(the cucumber spec language) that are then compiled into c# code. Nice reports, but I find the generated code hard to read... ie a bit too verbose ([example feature](https://github.com/techtalk/SpecFlow-Examples/blob/master/BowlingKata/BowlingKata-MbUnit/Bowling.Specflow/ScoreCalculationAlternativesFeature.feature) [example generated code](https://github.com/techtalk/SpecFlow-Examples/blob/master/BowlingKata/BowlingKata-MbUnit/Bowling.Specflow/BowlingSteps.cs)) however I wouldnt discard it totally.

	
  * NSpec:  You write c# code (very lambda-y)  and it generates reports.. like it even less for reasons similar to the above,  have a look at it yourself [here](http://nspec.org/)

	
  * Fit/fitnesse:  I haven't tried it, it supposed to be very good, I ll leave that one to you (would love some feedback on this if anyone reading did try it)




Unit Testing Frameworks.








	
  * xUnit: a nice, compact unit test framework, I like it because it has less noise,  no setup method (ie it uses the ctor for

	
  * nUnit:  The most popular one.

	
  * mbUnit: good support for RowTests.

	
  * _

	
  * msTests: the option by Microsoft. I tried this framework when it came out, so perhaps not valid anymore. My experience with it was that the same set of test ran 20% slower. Also it had poor support for theory tests. Maybe this all changed. I will guess that anyone using this framework does it because they can't use anything else




[![](http://roundcrisis.files.wordpress.com/2011/05/unit-testing-fm.png?w=202)](http://roundcrisis.files.wordpress.com/2011/05/unit-testing-fm.png)







Builds








	
  * Psake:  powershel based DSL for building

	
  * Rake:  Ruby based Dsl for builds, nice to use ruby, but sometimes needing the ruby dependency is a deal breaker

	
  * Nant: not something I would choose, but hey if you like xml this is the way to go (if you like Xml you might want to talk to your doctor too ;) )

	
  * MSBuild:  I find it non intuitive, I thought I was being unfair so I asked in twitter what ppl thought of it. One supporter and 4 not really happy with it (see below)

	
  * Final Builder : a commercial option, and not a bad one to be honest. Very easy to use (drag drop style) tho not as flexible as we needed.







[![](http://roundcrisis.files.wordpress.com/2011/07/capture.png)](http://roundcrisis.files.wordpress.com/2011/07/capture.png)







Code Coverage








	
  *  NCover: does the job but I think the generated graph could be better. Running the tool was cumbersome too as far as I remember

	
  *  dotCover : really nice and integrated with resharper, it a bit rough around the edges with lambdas and other minor things, but a tool I use day to day







Feedback and anything that wasn't mentioned yet , please feel free to comment




Cheers
