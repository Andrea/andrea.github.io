---
author: roundcrisis
comments: true
date: 2009-10-30 10:38:18+00:00
layout: post
slug: using-ninject-and-asp-net-mvc
title: 'Using Ninject and Asp.Net MVC '
wordpress_id: 418
categories:
- .net
tags:
- asp.net MVC
- ninject
---

If you are trying to use Ninject with Asp.net MVC, there is an integration available in github
http://github.com/enkari/ninject.web.mvc if you look at the code there its just 3 clases, but
the fact that its been used by much more people than just myself makes me a bit more confortable because
I m not terriby familiar with Asp.Net MVC. Please note I m not too familiar with Ninject either
If there is anything that can be improved, I m all ears.

Anyway, this is the integration working, using Ninject 2, I tried this with MVC 1 and 2 and they both worked.

Obviously get the code from the Github repository and build the solution in release mode, add them to your
project.

Then in your Global.asax.cs you need to do your implementation of   CreateKernel, and a really important step,
to register all your controllers, to do that just override the OnApplicationStarted with RegisterAllControllersIn("SomeAssemblyName")
as in the example there in github.

If you are not familiar with ninject you ll need to look at defining your Modules as well, something like

    
    private class MyWebAppModule : NinjectModule
    {
       public override void Load()
      {
          Bind<ISomething>().To<Something>();
    ......
      }
    }


Oh yeah, for some reason, kernel.AutoLoadModules() doesn't work for me, its not a feature I m interested in at the moment but ...

and you can use that module to create the kernel, there are other ways to use Modules but that worked for me
on my todo now is to understand why you would use one way over the other to create and work with modules
and what modules actually are.
