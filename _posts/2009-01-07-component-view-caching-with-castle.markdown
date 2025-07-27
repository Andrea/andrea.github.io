---
author: roundcrisis
comments: true
date: 2009-01-07 12:41:44+00:00
excerpt: Using caching on ViewComponent
layout: single
classes: wide
slug: component-view-caching-with-castle
title: Component View Caching with Castle
wordpress_id: 74
categories:
- castle
- monorail
tags:
- castle
- development
- monorail
---

I had to add some caching for a ViewCompoment in castle recently and, at least for me, it wasnt too clear what to do at first.

A ViewComponent is a very handy thing in castle, amongst other things it allows you to have  aView Component that can be, a login box, a menu,  an rss feed reader.  Sometimes the you need to cache the viewcomponent and this is how you need to go to this post by [hammet ](http://hammett.castleproject.org/?p=226)

I couldn't use the decoration
`
[ViewComponentDetails("comp1", Cache=ViewComponentCache.Always)]
`
because I needed the component to be refreshed every so often , so I used my own implementation
`
[ViewComponentDetails("BlogComponent", Cache = ViewComponentCache.UseCustomCacheKeyGenerator, CacheKeyFactory = typeof(YourCacheKeyGenerator))]
`

_YourCacheKeyGenerator _is a class that you create that must implement _IViewComponentCacheKeyGenerator _something similar to
`
public class YourCacheKeyGenerator: IViewComponentCacheKeyGenerator
{
public CacheKey Create(string viewComponentName, IDictionary parameters, IEngineContext context)
{
CacheKey key = new NamedCacheKey();
.....
..... your implementation here
return key;
}
`
I made my implementation dependant on time but you can make it dependant on anything you need

If there are any errors or comments please let me know
