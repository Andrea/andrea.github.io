---
author: roundcrisis
comments: true
date: 2010-09-12 15:40:31+00:00
layout: post
slug: irish-open-spaces-coding-day-iii-retrospective
title: Irish Open Spaces Coding Day III Retrospective
wordpress_id: 670
categories:
- .net
- code_shapes
---

Yesterday we had the 3rd IOSCD. It was great fun, the code is all available [here](http://www.assembla.com/code/ioscd/subversion/nodes).

 

The sessions

 

[![IMAG0142](http://roundcrisis.files.wordpress.com/2010/09/imag0142_thumb.jpg)](http://roundcrisis.files.wordpress.com/2010/09/imag0142.jpg)

 

 

and

 

[![IMAG0144](http://roundcrisis.files.wordpress.com/2010/09/imag0144_thumb.jpg)](http://roundcrisis.files.wordpress.com/2010/09/imag0144.jpg)

 

It was great to have some hardware to play with, people really seem to get a good kick out of that, there was a Netduino and two Lego NXT.

 

I m hoping that other people will tell us about their experience yesterday (hint hint ;) ). 

 

Some of the sessions included: Ruby on rails app for the book club assistance (called and_on_that_basis , no idea why), netdruino hacking with some sort of Rx , and then using Rx over the wire, finally i was working on something called Code Shapes.

 

Just starting a tool(?) that will analyse each class and draw a diagram:

 

  
  * Hollow Ellipse - public method 
   
  * Shaded Ellipse - protected, private, or package private method 
   
  * Rectangle - field 
   
  * Line - a use-dependency from a method to a method or a field.
 

as per [Michael Feather post](http://michaelfeathers.typepad.com/michael_feathers_blog/2010/08/testng-and-what-wed-like-code-to-be.html) on this. 
