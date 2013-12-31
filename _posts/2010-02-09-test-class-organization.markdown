---
author: roundcrisis
comments: true
date: 2010-02-09 21:29:05+00:00
layout: post
slug: test-class-organization
title: Test Class Organization
wordpress_id: 470
tags:
- unit-testing
---

Hi there

Just though I d share this

this is the way I ve been organizing my test code as of late


    
    
    
    
    	public class MyClassTests
    	{
    		public class Given_a_context
    		{
    			[Fact]
    			public void When_somthing_happens_Then_result()
    			{
    				throw new NotImplementedException();
    			}
    
    			//...............
    		}
    
    		public class Given_a_different_context
    		{
    			[Fact]
    			public void When_somthing_happens_Then_result()
    			{
    				throw new NotImplementedException();
    			}
    
    			//...............
    		}
    	}
    



I like this because you can still easily find the class name with resharper 
you can also separate the contexts you are testing in a more clean way
this works out good for me most of the times, even when you are inheriting 
from a base test class.
It also reads well in the Test runner.
Any comments?

