---
date: 2014-01-03 10:13:00
layout: post
title: MEF and AppDomains II
categories:
- MEF
- exception
- .net
---

Continuing from yesterday, I was testing how hard it is to work with two domains, I found [this][codepr] and it seemed like a good starting place. I started moving things around to understand how it all fits together, and soon I started getting remoting errors... it made me think, I really don't want remoting problems to be a normal type of problems you get when of developing plugins, however is not a dead option just yet.  

When using external dependencies in a composed application you can get a [*ComposablePartException*][ref-cpe] temporarily I added the dependency to the main project but I am hoping there is a better way to tell MEF about external dependencies that should be "brought in with a type".

BTW if you are playing with debugging capabilities and related, make sure you have the option "Just my code" in options not selected. If messing with appdomains check that the option for debugging other appDomains is enabled. 

Next I am actually trying to integrate this into the project (i.e. where I want this to work) and see what breaks

The convention based stuff in MEF is truly simple. You use a [RegistrationBuilder][regb] to set what types we are interested in, in my case I wanted to get all types derived from an interface, but I tested with a base class and it worked too, when you are doing that you can create a part builder (as below) and this is where you can set the [creation policy][cre-pol] which helps when you need to set whether there is one shared instance between many imports or you create one per each importer.

{% highlight c#%}
	var classPartBuilder = regBuilder.ForTypesDerivedFrom<MyClass>();
	classBuilder.SetCreationPolicy(CreationPolicy.NonShared);
{% endhighlight %}

When you want to get the exports you can use a [DirectoryCatalog][dir-cat] like this

{% highlight c#%}
	var catalog = new AggregateCatalog();
	//PluginRelated is the type where all this code lives
	catalog.Catalogs.Add(new AssemblyCatalog(typeof(PluginRelated).Assembly, _registrationBuilder));
	var directoryCatalog = new DirectoryCatalog(PluginPath, _registrationBuilder);
	catalog.Catalogs.Add(directoryCatalog);
{% endhighlight %}

if you want to get the exported types you get a container and compose it 

{% highlight c#%}
	var container = new CompositionContainer(catalog);
	container.ComposeExportedValue(container);
	var exports = container.GetExportedValues<Component>();
{% endhighlight %}

ok, so I hit the dependencies problem, need to read more about this. 


[codepr]:[http://www.codeproject.com/Articles/633140/MEF-and-AppDomain-Remove-Assemblies-On-The-Fly]
[ref-cpe]:[http://msdn.microsoft.com/en-us/library/system.componentmodel.composition.primitives.composablepartexception(v=vs.110).aspx]
[regb]:[http://msdn.microsoft.com/en-us/library/system.componentmodel.composition.registration.registrationbuilder%28v=vs.110%29.aspx]
[cre-pol]:[http://msdn.microsoft.com/en-us/library/system.componentmodel.composition.creationpolicy%28v=vs.110%29.aspx]
[dir-cat]:[http://msdn.microsoft.com/en-us/library/system.componentmodel.composition.hosting.directorycatalog%28v=vs.110%29.aspx]
