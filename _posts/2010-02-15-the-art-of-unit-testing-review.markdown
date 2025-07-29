---
author: roundcrisis
comments: true
date: 2010-02-15 07:39:04+00:00
layout: single
classes: wide
slug: the-art-of-unit-testing-review
title: The Art of Unit Testing - Review
wordpress_id: 443
tags:
- unit-testing
---

A few of us have been reading this book as a part of a book club. Finally I think is time to push a review for this book .

Let me start saying that my expectations for the book were **very** high, the book club helped because we were really reading it in depth and going over little bits of each chapter.

**Bad things about the book**

Examples are not great, there are errors on some of them, and (possibly the worse thing of it all) some of the tests dont follow the advice that is given in the book, particularly in naming convention.

If you download the code that accompanies the book, some of the tests (that are supposed to pass) fail.

We sent an email with corrections but never heard back ( not sure if they didnt get it or what), which, to be honest, was a bit disappointing, if this code was on github I would have forked it just to get it fixed, tho I'm not sure Is correct to do that if the code is not on github (if anyone knows please let me know).

Again on the code samples, some of the examples scenarios are not really that descriptive, I have to add, that after preparing the talk I gave in DDD, I have to say its really really hard to come up with good sample code, that demonstrates a smell and a solution in a clear way in not a lot of code... so maybe its not a fair criticism, but I really had to mentione it, because you read the sample and really **wtf? **a bit .

The chapter on Mocking is not great either, Rhino mocks is not used in anger, and I'm pretty sure Roy could have gotten someone with loads of experience in Rhino Mocks to look and review (and improve ) the example code.

**Good things about the book**

I know that after what I said what bad in the book, this will sound fake, but I actually think the book is **really** good, because I learned **loads** about unit testing.

It made me think about how to test, What to think about when testing, how to approach writing code with testing in mind.

It basically gave me a lot of basics like, the difference between Unit and integration tests, and that was important, because I could clearly define, I need to tests **this **(whatever it is you are writing) I understood the differences between different [Fakes](http://martinfowler.com/articles/mocksArentStubs.html),  as well as the difference between state and behavioural tests.

Along the way, you pick up on test smells, and many tips on what to do and most important, what not to do.

Since I read the book I understand and I have the purpose of writting code ( test code included of course) , that is readable and maintainable. And I want to **trust **my tests, and thanks to the book, I can now understand why these are important qualities of the code.

The funny thing is, that since then, I actually feel like I really got how to be test driven, because writing code in any different way, simply doesn't make sense any more.

**Conclusion**

A really good book if you are interested in unit testing and feel the need to learn how to do it better, like anything you read, take it, use what you can and completely believe in and then, discard the rest; even then you will have about 80% of the book (or more) really valuable.

Reading this book, along with [TDD by example](http://www.amazon.com/Test-Driven-Development-Kent-Beck/dp/0321146530) by Kent Beck and maybe completing it with [xUnit Test Patterns](http://xunitpatterns.com/) byMeszaros
