---
author: roundcrisis
comments: true
date: 2008-07-23 19:58:00+00:00
layout: post
slug: nvelocity-creating-urls
title: NVelocity - creating urls
wordpress_id: 36
categories:
- NVelocity
---

I always forget these two:  
  
$Url.Link('label', "%{controller='controllerName',action='actionName'}")  
  
and this:  
  
To Create a form  
  
  
$Form.FormTag("%{id= 'formId', action='save', immediate = 'true'}")  
$Form.EndFormTag  
  
I really wished there was a MR RC4 :D
