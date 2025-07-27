---
author: roundcrisis
comments: true
date: 2010-02-12 01:02:01+00:00
layout: single
classes: wide
slug: push-on-green-deployment-brain-dump
title: Push on Green Deployment - (Brain Dump)
wordpress_id: 462
tags:
- deployment
- development
- push-on-green
---

The other day I was listening to Kent Beck in [this podcast](http://www.cincomsmalltalk.com/blog/blogView?showComments=true&printTitle=Industry_Misinterpretations_164:_Going_for_the_Longball&entry=3436948975) where he was talking about, amongst other things, push on green deployment, basically the idea is that once your test suite goes green, you deploy.

When I heard  this originally I thought :

1) Think about all possible problems -> not only technical( this component is not compatible with the component just rolled out, etc, etc)  but also processes ( and people using them ) this is a real concern, because the pace of change would increase I would guess)

2) What tests? Who wrote them? I would think higher level tests? actually all tests? Possibly the upside of this is that companies that produce quality software will become incredibly popular ( "My software doesn't brake, we test throughly" could actually be part of the marketing and backed by actual tests, imagine that)

3) The premise for push on green is basically to push Software Development practices up a notch, so that as a developer we can say we are delivering a feature on a particular date and we can do that confidently, How does push on green help us deliver as we promised, would it makes us slower?

Deployment is a painful process, and often neglected topic, as a developer how often do you think about it? And worse, How many times you just don't know what will happen? Most importantly. How stressed do you get close to going live? (I guess this is the time when we all start thinking about it seriously)

Great, now imagine What if that would happens every **hour**?

In the beginning it would be scary, but then, the practices need to be polished enough so it becomes something normal, that you are not only used to , but confident about it. After all we all become better at things with practice.

Do i like the idea? Yeah! and Its as scary as it gets :) Lets look into it more in depth


## So how can this possibly work?


If I was going insane(er?) and really wanted to do this, as a C# developer, what is possible?

Maybe I would start of an continuous open beta or, edge (somehow warning my users of the fact that the code they are using is "fresh out of the oven") and once I see some stability (perhaps people could vote for it or similar)then I can fully deploy.

But then thats is just my application, lets imagine I produce code that is not public facing, but that , its an API, consumed by many other applications, how would they be aware and **react** to interface changes? More importantly, would this make software evolution slower  by persisting everlasting APIs? or would it induce APIs that are very noisy, hence harder to discover?

I m asking this because:   lets forget about the barrier of web or desktop for a minute and focus on dlls, where they live and how we use them and consume them.

If my Operating System vendor/framework provider makes a push do i want my app to get that immediately?

Say I m using an interface something like IEmailSender, that has the methods Send(IEmailTemplate, ISomethingElse) and that is replaced for the better designed IEmailSender.Send(Message) with the Send(Message[]) overload. In that example I agree with the change, I want to use the new code because the contract is better (lets assume we all agree is better ok); however, that would mean changing my application, re testing all those areas where I use IEmailSender and I most likely don't want that.

I have to add, I would probably want to do an integration test anyway, or should I blindly trust the new IEmailSender implementation because we are all pushing on green now?

So the option here seems to be, create the new contract but maintain the old one around for a while right?, but then your API will have all these Send methods, and that doesnt seem to be going into the better development practices direction

Next I m gonna try heroku in anger and see if I get more ideas from using it, heroku is a service that runs ruby applications that are deployed when you commit.

This is a brain dump on this and would love to hear thoughts from other people, corrections, feedback, etc always welcome :)
