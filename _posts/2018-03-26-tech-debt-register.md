---
author: roundcrisis
comments: true
date: 2018-03-27 10:48:00+00:00
layout: single
classes: wide
title: Techdebt register
categories:
- techdebt
---

There is really no hard and fast rule for recording technical debt, some people do it on their bug trackers, others in their agile/kanban boards, storing it in a text file with the code is another way. The reason why this can be helpful is because technical debt can be committed with the code, also code can be reviewed with it, giving it extra context.
You could simply record this in a file as separete paragraphs, however I have been thinking that standardising the format might help. This template is somewhat inspired by [this article](https://insights.sei.cmu.edu/sei_blog/2016/06/got-technical-debt-track-technical-debt-to-improve-your-development-practices.html), I was compelled to introduce some  modifications to it, keeping it small enough to be able to record tech debt fast. 

It might be tempting to think that a template is not needed but I digress, without a template:

* it can be hard to know what we should record, how much detail is needed. 
* the technical debt is inconsistent and it can be hard to review stopping often to find the contextual information needed.

## Technical debt item 

- *Name*: (high level of this tech debt)
- *Description*: (a long form description of the technical debt, can suggest possible solutions if suitable)
- *Date*: (creation of this technical debt record)
- *Creator*:  (of this note so that they can answer questions)
- *Location*: (repo & filename or module)
- *Complexity*: (from 1 to 5 how hard would it be to solve the problem NA if you don't know and want the group to evaluate)
- *Reward*: (from 1 to 5 where 1 is a nice to have and 5 is a significantly measurable improvement both from a performance, security, complexity,etc point of view)


Example:

- Name: The module X uses external services in a non-resilient way
- Description: module X uses kitt.ie, monkeysjumpingaround.io and boringbutusableapi.com  for verification purposes in at least 3 areas of the code, the call to these external services is duplicated and, on failure, at best we log the error (at worst, the system fails silently). 
- Date: 01/03/2018
- Creator: Cat Otterson
- Location: X files, Integrations module
- Complexity: 3
- Reward: 4


