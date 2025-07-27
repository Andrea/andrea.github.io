---
author: roundcrisis
comments: true
date: 2008-07-07 16:03:00+00:00
layout: single
classes: wide
slug: small-but-interesting-find
title: Small but interesting find
wordpress_id: 33
categories:
- NHibernate
---

Yesterday I was coding and I needed to create a criteria like  
  
```
Repository.FinOne(Restriccions.Eq("Email", email));  
```  
  
however I wanted to make sure that there was not problems with casing. It turns out `IgnoreCase` exists and can be used this way :D  
  
```
Repository.FinOne(Restriccions.Eq("Email", email).**IgnoreCase**());
```
  
I was really happy to find this, thanks NHibernate in Action!
