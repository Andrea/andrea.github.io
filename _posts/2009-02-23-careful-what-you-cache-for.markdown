---
author: roundcrisis
comments: true
date: 2009-02-23 18:07:05+00:00
layout: single
classes: wide
slug: careful-what-you-cache-for
title: Careful What you Cache For
wordpress_id: 162
categories:
- NHibernate
tags:
- caching
- NHibernate
---

Had a DetachedCriteria, very simple,  I check it running with  profiler side by side  and I see loads of queries running. Why?

The criteria was something like this 
`
var criteria = DetachedCriteria.For<MyEntity>()
.SetCacheable(true)
.SetCacheRegion(CacheRegions.RarelyChanges)
.SetFetchMode("Things", FetchMode.Eager)
.AddOrder(Order.Asc("Name"));`

I was trying to cache a criteria for MyEntity and have an eager fetch mode for  Things ( a collection of Thing) ,  so, it turns out that i have an n+1 .

In the view, there was an iterator in the Things Collection, so  just to confirm I removed the reference in the view to this and profiler was running the expected queries(no n+1). 

removed the references to caching in the criteria  just to see what was happening, an the resulting query was getting what it supposed to get,  added the call in my view for each Thing in the Things Collection perfect, the query was running fine and not doing the n+1 .

I decided to leave caching out just this one time and I'm writing this post to remind myself to check exactly why this is happening, or maybe someone will have the answer already?

Can't remember the definition of MyEntity, might add it to comments later
