---
date: 2014-05-05 14:13:00
layout: post
title: Behaviour trees first attempt at implementing in F sharp
categories:
- programming 
- development
- f sharp
---

Recently I saw a post about a simple FSM implementation in F# ([link][fsmf]), and that got me thinking about our Behaviour Trees and how simple or complex it would be to implement them in F#. 

##What are behaviour trees?

There is a longer intro to the topic [here][adba] and a more extensive one in this [paper][pape]. 
What I remember when I think about them is that there are 2 types of constructs:
 
Actions and conditions: Actions are changes in the game world  such as animation plays, health decreased, etc. Conditions check certain states of the world. 

Sequences and selectors: This is how we link and order the *actions* and *conditions*. Sequences pretty much are what your intuition tells you, they run a sequence of actions or conditions (they all need to return true). Selectors are the flipside of sequences, they run until something returns true.

To refresh the old noodle (ie: my brain) I implemented a very simplistic behaviour tree in C#. It looked like this (there are many classes in one file... you will survive), you can see it [here][csbt]


## F# implementation 

I tried starting implementing the selector, no luck. I couldn't figure out what it should look like. 
Then I tried starting at the top, implementing the implementations of the actions mostly because it was the functions I knew how to implement, and they might guide me to somewhere interesting. 

Turns out it pointed me to my total lack of understanding of the F# type system.

##Types

It turns out I had to leave my very practical approach to learning F# and go get my read on. I heard that F# has a pretty advanced type system, and I was just about to learn why.

Turns out there is an [amazing series of posts about types][scott] by Scott Wlaschin. I think there is little point in my replicating what he said in worse prose :D, so go read that, and if you know of another cool link on the F# type system, please let me know by leaving a reply to this post.

Anyway, after a glance at the posts I think I need a discriminated union, or maybe a class but that feels dirty, of course I'll have to try both. 

[Here I took a rather long pause to go and read the posts properly and then do the Koans on records and classes to get my brain warmed up,] 

Then I attempted to implement the tree again but getting stuck again. I decided some procrastination might help so, I went to look for some implementations of BT in every functional language I could think of and found these [one in clojure][cloj] (I think these might be slightly different Behaviour Trees), and this [one in common Lisp][clisp].

I am going to leave this for today but will return with a solution as soon as I get one.



[adba]:http://www.altdevblogaday.com/2011/02/24/introduction-to-behavior-trees/
[fsmf]:http://withouttheloop.com/articles/2014-04-18-fsharp-csharp-statemachines/
[pape]:http://www.doc.ic.ac.uk/teaching/distinguished-projects/2009/c.lim.pdf
[scott]:http://fsharpforfunandprofit.com/posts/overview-of-types-in-fsharp/
[cloj]:https://github.com/nakkaya/alter-ego
[clisp]:https://bitbucket.org/eeeickythump/behave-tree
[csbt]:https://gist.github.com/Andrea/5b8dfa9daff76ffcf3b9