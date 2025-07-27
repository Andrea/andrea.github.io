---
author: roundcrisis
comments: true
date: 2010-09-22 19:11:20+00:00
layout: single
classes: wide
slug: projects-organization-how-to-organize-assemblies-in-your-local-machine-to-avoid-nightmares
title: Projects Organization - How to organize assemblies in your local machine to
  avoid nightmares
wordpress_id: 690
categories:
- Best Practices
tags:
- dll assemblies layout
---

This is just how I organize folders and projects on my machine, there are endless possibilities , but I saw someone searching for it online and it did took me a long while before I settled on this, so I thought I would blog about it.

This can be a good or bad way of organizing, I think it depends on the kind and number of projects you are working on

Imagine you have a folder that contains the following folders



	
  * **code** (Real code, shipable, or company proof of concepts with its own repo)

	
  * **spike **(test to see if something works, Proof of concepts very basic)

	
  * **third-party** (OSS libraries and frameworks, etc)


Inside my **code** folder, each solution has it’s own **Lib** or **Libs** or **Libraries** folder (eg One Lib folder per solution ). The story is very different in **spike **since I put projects there for stuff I never ever want to ship then I have a shared **Lib** or **Libs** or **Libraries** folder where I put everything I ever needed. In third party I leave as I got from source control .

Inside the Libraries folder I mostly try to keep a folder per project and inside a folder per version, something similar to this

[![Capture](http://roundcrisis.files.wordpress.com/2010/09/capture_thumb1.png)](http://roundcrisis.files.wordpress.com/2010/09/capture2.png)

if in doubt copy the assembly, disk space is cheap.
