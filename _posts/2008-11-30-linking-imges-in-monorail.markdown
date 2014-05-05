---
date: 2008-11-30 17:56:00
layout: post
title: Linking images in Monorail
categories:
- monorail
- NVelocity
- urlHelper
---
A quick one

Say you have an image or god knows what and you need to add a link to it, in html you'll do something like:


{% highlight html linenos %}

<a href="http://foo.bar/something.html">
	<img src="..." /> 
</a>
{% endhighlight %}
    
    In a view you can do this:

{% highlight html linenos %}    
<a href=$UrlHelper.For("%{ controller='product'}")>  
    <img src="$!Image.Path" alt="$!Name" />
</a>
{% endhighlight %}