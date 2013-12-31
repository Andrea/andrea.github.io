---
author: roundcrisis
comments: true
date: 2009-12-17 21:30:51+00:00
layout: post
slug: step-by-step-startersts-setup
title: Step by Step StarterSTS Setup
wordpress_id: 436
tags:
- Geneva
- starter_sts
- WIF
---

I m planing on a series of blogs on WIF ( windows Identity Foundation) however that might or might not happen :), so meanwhile I  m posting this, StarterSTS is as the name implies a starter sts something to get you started on the world of Federeation Identity , claims and all that lovely stuff.

You can find a video about all this steps in the[ codeplex site ](http://startersts.codeplex.com/)to starter STS, however there are a few differences between what you can see in the config files there and whats in 0.95 ( this is what I've used)  .

I tried this on a Windows 7 and a Server 2008 machine

1) Get the sources from codeplex and copy them over somewhere. create a web app that points to it
2) Create a new app pool ( not necesary but nice to be able to see what is happening)
3) Install WIF (used to be called geneva framework)  latest binaries available [here ](http://www.microsoft.com/downloads/details.aspx?FamilyID=eb9c345f-e830-40b8-a5fe-ae7a864c4d76&displaylang=en#filelist)
4) Download and install SQL server express,or if you have a ssql server there happy days :D
5) Create a self signed cert and add it to the default web site , then go to default website and add the certificate to https with Bindings options
6)  Add read access to the Network service account in the folder where you put the sts sources
7) Run mmc -> add snap in and get the cert thumb print , also set the network service read permisions by right click Manage Private Keys...[![](http://roundcrisis.files.wordpress.com/2009/12/snapin.png?w=237)](http://roundcrisis.files.wordpress.com/2009/12/snapin.png)
8) Open the file config/Certificates.config and change the thumbprints of the certificates ( initialliy they are all the same , the last one RP, should be the thumbprint with all spaces removed) (you can get the thumbprint of the certificate in mmc ->certificate ->properties -> thumbprint)
9) Run aspnet_regsql ( to create the asp.net membership provider aspnetdb) (This program is not in the path, so you ll probably have to go to C:\Windows\Microsoft.NET\Framework\<your version of the .net framework, if in doubt go to 2.0>>**aspnet_regsql** )
10) Create some users from IIS Maanger.
11) If you are going to be using from somewhere other than localhost:



	
  * The self cert you provided must be added to your the trusted providers( whereever you are using this)


	
  * when you are using fedutil make sure teh references to the federationmetadata.xml points to your server and not localhost ( i seen this happening more than once)



12) On the application side of things Add STS reference...
13) you might need to tweak the startersts.Config
