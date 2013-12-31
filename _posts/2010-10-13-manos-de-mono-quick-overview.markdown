---
author: roundcrisis
comments: true
date: 2010-10-13 20:00:45+00:00
layout: post
slug: manos-de-mono-quick-overview
title: Manos de Mono - Quick overview
wordpress_id: 704
categories:
- unit-testing
- web-development
tags:
- manos_de_monos web web-development
---

I heard about this new web framework the other day, the code its available on [github/jacksonh/manos](http://github.com/jacksonh/manos) the main interesting thing I heard about it were:



	
  * runs on Mono

	
  * Has its own server

	
  * Has no dependecies on Asp.net

	
  * the main goal of mono is to simplify web application development

	
  * routing appears to be simpler ( to use and test)

	
  * command line for managing your apps (deployment included)


At this point, I wanted to see some code, I went to the example on github and I was pleasantly surprised


[sourcecode language="csharp" padlinenumbers="true" collapse="false"]
//
	// A mango application is made of MangoModules and MangoApps
	// There really isn't any difference between a Module and an App
	// except that the server will load the MangoApp first. A mango
	// application can only have one MangoApp, but as many MangoModules
	// as you want.
	//
	public class MangoProject : MangoApp {

		public MangoProject ()
		{
			//
			// Routing can be done by using the Get/Head/Post/Put/Delete/Trace
			// methods. They take a regular expression and either a method
			// or another module to hand off processing to.
			//
			// The regular expressions come after the method/module, because
			// Mango uses params to allow you to easily register multiple
			// regexs to the same handler
			//
			Get (Home, "Home");

			//
			// The Route method will hand off all HTTP methods to the supplied
			// method or module
			//
			Route (new DocsModule (), "Docs/");
		}

		//
		// Handlers can be registered with attributes too
		//

		[Get ("About")]
		public static void About (MangoContext ctx)
		{
			//
			// Templates use property lookup, so you can pass in
			// a strongly typed object, or you can use an anonymous
			// type.
			//
			RenderTemplate (ctx, "about.html", new {
				Title = "About",
				Message = "Hey, I am the about page.",
			});
		}

		public static void Home (MangoContext ctx)
		{
			RenderTemplate (ctx, "home.html", new {
				Title = "Home",
				Message = "Welcome to the Mango-Project."
			});
		}
	}
[/sourcecode]







	
  * Like the module and App ideas

	
  * like the simplicity of the code above

	
  * seems to work at a slightly lower level of abstraction than MVC but I can live with that

	
  * Interesting that it uses it's own template engine, the syntax is nice, but I wonder why not spark, razor, nhaml, nvelocity. After all, It would be cool to use what I know already. Will have to find out.


Will have to do some more research on it
