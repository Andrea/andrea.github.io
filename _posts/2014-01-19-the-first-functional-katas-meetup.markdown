---
date: 2014-01-21 22:44:00
layout: post
title: The first Functional Katas meetup
categories:
- f#
- functional programming
- scheme
- clojure
- meetups
- usergroups
---

The first [Functional Katas][fk] happened last Wednesday, out of 29 people who signed up, about 15 turned up. Which is great given that it's January and cold, and it was raining. An interesting part of going to the kata is that there is no internet access, this is somewhat a problem, at the same time, I kinda liked that extra constraint, perhaps not all the time.

There are a few things I learned from being there. I was pairing with Kevin, who was writing [Clojure][clojure], a dynamic programming language that targets the jvm (I learned later it also can compile to js and apparently there is an implementation on the clr too), my first impression was that although very powerful ... so many parentheses! I guess it is a trait(?) of Lisp, in saying all this please keep in mind I am ignorant in the ways of Lisp so this is truly first impression. It was fun to go and try to do this in a language I had no idea about.

![clojure]({{ site.images }}/2014-01-21-clojure-icon.gif)

After 50 minutes of writing code, we went over all the solutions, I was really impressed about this. We had solutions in Haskell, Scala, F#, Scheme (with Racket) Erlang and Clojure. 
One thing that I noticed as we went through the solution is how similar the approaches to solve the problem were, pattern matching is a wonderful feature of functional languages. The code in all the solutions was rather elegant, actually you can take a look at them at our [github repo][fk-git] 

One of the solutions really got me thinking though, the one in Erlang ([code][erl-sol]), when describing how the solution was developed, Phil explained that he knew that argument parsing will be a problem so he created little abstractions that he could test from, once the actual problem of the kata was solved, he dealt with the problem of parsing arguments. What I can't stop thinking about is, is this type of thinking generated/helped by Erlang and it's programming model? (Phil's day job is on Erlang). I had planned to learn Erlang in the not so distant future, I think this question just raised the priority :D.

Anyway, that is all. The next kata meetup is on the 19th of February, I am really excited about it, if you want to come, registration and more info [here][fk-2]. We talked about trying to solve a smaller problem, so that we can have more time to show and discuss at the end. 



[fk]:http://functionalkats.tumblr.com/post/70587488630/first-meeting-trinity-college
[clojure]:http://clojure.org/
[fk-git]:https://github.com/FunctionalKatas/Katas
[erl-sol]:https://github.com/FunctionalKatas/Katas/blob/master/2014-01-Calculator-Erlang/calculator.erl
[fk-2]:http://functionalkats.tumblr.com/post/74080235065/february-meeting-19th-february