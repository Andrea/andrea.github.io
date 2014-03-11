---
date: 2014-03-10 12:13:00
layout: post
title: The importance of win times
categories:
- programming 
- development
- how I learn
---

As most developers I have really good and really bad days, it comes with the nature of the job. Lately I have been thinking that I had a lot of bad days, I needed to feel like I was wining and so I solved a small totally unrelated problem, I felt good. It will surprise no one that after that I was able to suck a little less during that day. 
Solving that little thing gave me a little bit of confidence I needed. 

This event made me think about he amazing book ["Zen and the art of motorcycle maintenance"][aomm], I don't remember who said it was the best software development book ever, so I read it last year, and I was thinking about it for a long time. The focus on the book is on quality and what that actually means, in the end you get a general sense about it, not a real answer.

Just for the craic, this is a quote from the book: "Some things you miss because they are so tiny you overlook them. But some things you don't see because they are so huge"

For some reason this reminds me of something I just did, and that is when you find a potential error, instead of just throwing an error, also try to suggest a solution in the error message... NullException is the most recurrent one

{% highlight c# %} 

	var player = Scene.Current.FindComponent<Player>().GameObj;
	if(player == null)
	{
		Log.Game.WriteWarning("A player is required for this behaviour to work, please add one.");
		return;
	}

{% endhighlight %}

In this case this makes sense because this message is for people of a team that is small and the language is informal. I don't need to do much other than let them know, you might want to react in a more suitable way. Quality is contextual.


[aomm]:http://en.wikipedia.org/wiki/Zen_and_the_Art_of_Motorcycle_Maintenance