---
date: 2014-03-29 23:13:00
layout: single
classes: wide
title: Dojo fractal forest in F# (with pictures)
categories:
- programming 
- fsharp
- fractals
---

A week or so ago I was lucky to be in San Francisco for "the" Game Developer Conference, while I was there I was able to meet [Mathias Brandewinder][mb], we got to chat about loads of things (and eat some really nice breakfast) two of the many things we talked about were FsCheck and the dojo fractal forest.

FsCheck is this really cool [Pex][pex] like tool, I am trying it out and I could attempt to explain it but Mathias already wrote a great post about it in [this post, check it out][fscheck]. You can also use FsCheck with NUunit.

 The [Dojo fractal forest][djf] is just a little exercise in F# to make a tree using recursion, I though I should give it a go, it looked like fun.

 As I was writing this I was debating weather I should put some code up or not, as it might have a negative effect on people thinking of doing this. I decided against it for the moment. These are the iterations of the trees I built. 

![tree ](http://cdn.makeagif.com/media/3-29-2014/ETACjx.gif)

 When I reached the tree I was happy that I had achieved the goal of the exercise, but what else could I do with it? 

 * Could I give it some leafs?
 * Could I grow the leafs over time?
 * Could the colour of the tree change with age (into a multi-coloured tree, because that seems way more fun)

Adding a leaf at the end of each branch was super simple, but that is not how trees work. I had to go find how real trees worked

![with leaf]({{ site.images }}/2014-03-29-trees-with-leaf1.JPG)

I need to continue this post later, if you are intrigued you should go and try it out yourself :) 


 [mb]:http://clear-lines.com/
 [pex]:http://research.microsoft.com/en-us/projects/pex/
 [fscheck]:https://github.com/fsharp/FsCheck
 [djf]:https://github.com/c4fsharp/Dojo-Fractal-Forest