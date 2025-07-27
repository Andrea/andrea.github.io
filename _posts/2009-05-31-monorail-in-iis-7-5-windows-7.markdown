---
author: roundcrisis
comments: true
date: 2009-05-31 13:23:56+00:00
layout: single
classes: wide
slug: monorail-in-iis-7-5-windows-7
title: Monorail in IIS 7.5 (windows 7)
wordpress_id: 259
categories:
- IIS
- monorail
- web-server
tags:
- iis7
- monorail
---

So I made the leap the other day and installed RC for Windows 7 and it all seems pretty ok.

Of course i had to do the _install all I need_ dance.

Making monorail work in this new version of IIS...well I just thought I d blog about it as it didn't work "out of the box".

One (obvious)  thing that you have to make sure you do is that you actually have asp.net and  the ISAPI module installed (its not by default).![application.jpg](http://roundcrisis.files.wordpress.com/2009/05/application.jpg?w=300)

The Virtual Directory needs to be an Application, for this you have an option for SetAsApplication in IIS in the contextual menu for the Virtual Directory.

IIS 7 has classic and Integrated mode, a very basic difference between these two modes is that in classic mode Asp.net was integrated into IIS via the ISAPI Extension, with the integrated mode asp.net runs natively, to read more about it check [here](http://learn.iis.net/page.aspx/244/how-to-take-advantage-of-the-iis7-integrated-pipeline/). That leaves me with the question of: Does that mean my app doesn't actually need ISAPI at all (that i will answer later, tho probably not).

All that said and you have to add the following to the web.config in system.webserver -> handlers

`<add name="MonoRail" path="*.rails" verb="*" type="Castle.MonoRail.Framework.MonoRailHttpHandlerFactory,Castle.MonoRail.Framework" preCondition="integratedMode" />`

` `

(of course change the handler to suit your self)

I have to admit, dont find setting up servers entertaining at all.

Hope it helps you.

Cheers
