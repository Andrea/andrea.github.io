---
author: roundcrisis
comments: true
date: 2008-11-30 17:56:00+00:00
layout: post
slug: linking-imges-in-monorail
title: Linking imges in Monorail
wordpress_id: 50
categories:
- monorail
- NVelocity
- urlhelper
tags:
- castle
- development
- monorail
---

A quick one 

Say you have an image or god knows what and  you need to add a link to it, in html you ll do something like



    
    <span class="kwrd"><</span><span class="html">a</span> <span class="attr">href</span><span class="kwrd">="http://foo.bar/something.html"</span><span class="kwrd">></span>
    <span class="kwrd"><</span><span class="html">img</span> <span class="attr">src</span><span class="kwrd">="..."</span> <span class="kwrd">/></span> <span class="kwrd"></</span><span class="html">a</span><span class="kwrd">></span>
    
    in a view you can do this
    
    <span class="kwrd"><</span><span class="html">a</span> <span class="attr">href</span>=$<span class="attr">UrlHelper</span>.<span class="attr">For</span>(<span class="kwrd">"%{ controller='product'}"</span>)<span class="kwrd">></span>  
        <span class="kwrd"><</span><span class="html">img</span> <span class="attr">src</span><span class="kwrd">="$!Image.Path"</span> <span class="attr">alt</span><span class="kwrd">="$!Name"</span> <span class="kwrd">/></span>
    <span class="kwrd"></</span><span class="html">a</span><span class="kwrd">></span>
