---
date: 2014-01-02 16:13:00
layout: post
title: MEF and AppDomains
categories:
- MEF
- AppDomain
- .net
---

The last few days I've been playing with MEF.

MEF is pretty cool, it allows you to recompose your application on the fly so I thought I should try it, I ended up looking at ["The Way of MEF"][way-of-mef], a series of samples from Glenn Block, pretty good to look at some code and understand what can you do in a clear way. I wish there was a video to go with it because you get the sense that he had a lot to say while those slides were rolling. Anyway, the samples were great, 

I think there are better places to learn about MEF, I compiled a bundle of links [here][mef-bundle], some cool things
-  MEF is available in .net 4.5 
-  it uses a convention based config if you want (I m sure a lot of work has gone into it)
-  With MEF you can deal with unknown types and can fetch new types from a catalog (I tried the assembly catalog only so far)

What I am trying to achieve is to be able to reload new versions of a type on the fly, not only at runtime, at debug time too. The first part is possible within one AppDomain, however not so, the second part (the debuggin part) you can see some code I was trying this with in [this github repo][github-temp-mef] (this is really one of the samples from Way of MEF, with a few changes but nothing big). I am sure you are wondering, why, why is it not possible to Debug? Well, it depends :) you can actually debug a little bit but as soon as you start trying to reflect on types you hit the error: "The type &lt;your type&gt; is available in both assembly.dll and assembly.dll" this points to a solution with multiple AppDomains, and I am trying to avoid that. 

I ll report again when I figure what is the impact on my case for multiple AppDomains or if I find an alternative solution.

[way-of-mef]:[http://codebetter.com/glennblock/2010/06/13/way-of-mef-slides-and-code/]
[mef-bundle]:[http://bitly.com/bundles/roundcrisis/5]
[github-temp-mef]:[https://github.com/Andrea/TempMEF]
