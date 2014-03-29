---
date: 2014-03-29 23:13:00
layout: post
title: Dojo fractal forest (with pictures)
categories:
- programming 
- development
- f sharp
---

A week or so ago I was lucky to be in San Francisco for "the" Game Developer Conference, while I was there I was able to meet [Mathias Brandewinder][mb], we got to chat about loads of things (and eat some really nice breakfast) two of the many things we talked about were FsCheck and the dojo fractal forest.

FsCheck is this really cool [Pex][pex] like tool, I am trying it out and I could attempt to explain it but Mathias already wrote about a great post about it in [this post, check it out][fscheck].

 The Dojo fractal forest is just a little exercise in F# to make a tree using recursion, I though I should give it a go, it looked like fun.

 As I was writing this I was debating should I put some code up or not, as it might have a negative effect. I decided against it for the moment. These are the iterations of the trees I built. 

![tree ](http://cdn.makeagif.com/media/3-29-2014/ETACjx.gif)

 When I reached this tree I was happy that I had achieved the goal of the exercise, but what else could I do with it? 
 	* Could I give it some leafs?
 	* Could I grow the leafs over time?
 	* Could the colour of the tree change with age (into a multi-coloured tree, because that seems way more fun)

Adding a leaf at the end of each branch was super simple, but that is not how trees work. I had to go find how real trees worked


 [mb]:http://clear-lines.com/
 [pex]:http://research.microsoft.com/en-us/projects/pex/
 [fscheck]:https://github.com/fsharp/FsCheck