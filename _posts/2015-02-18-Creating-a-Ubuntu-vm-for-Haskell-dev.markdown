---
date: 2015-02-19 11:44:00
layout: post
title: Creating a vm for Haskell development
categories:
- programming 
- development
- ubuntu
- Haskell
---

It has been a while since I used any flavour of Linux as a development environment (so, apologies if I am showing something really obvious). Haskell development in Windows doesn't seem to be the default :D (Haskell Platform installs and runs super well on Win7 and 8 BTW) but trying to learn in a non recommended environment is probably not a good idea. To that effect I am creating an Ubuntu vm to serve as a development environment for Haskell

These are the steps I went through: 

* Install virtualBox
* Used Vagrant to get a desktop Ubuntu (tho probably it would have been easier to just install from iso)
* I started of with a 64bit machine but something went wrong along the lines (convoluted) and decided to start again
* The machine was Ubuntu 12 I used Ubuntu Software updater to update to 14.04, the current version.
* From there I could sudo apt-get all the way to install Haskell Platform this way , this installed ghci 7.6.3
* I also installed [leksah](http://packages.ubuntu.com/trusty/leksah) as suggested by [@bodil](https://twitter.com/bodil), thanks :D
* When I tried to create a cabal sandbox I hit a problem, the update looked fine (ie no errors ) but the cabal version remained at 1.16 :(. To do a cabal update you have to call
```
cabal update
cabal install Cabal cabal-install 
```

* Thanks to [@TailCallingDev](https://twitter.com/tailcallingdev) (btw check out his blog, seriously), I had to add cabal to the path like this:

in .profile 

``` 

# set PATH so it includes cabal
if [ -d "$HOME/.cabal/bin" ] ; then
    PATH="$HOME/.cabal/bin:$PATH"
fi

```

Also the version of ghc I was on doesn't play nice with cabal > 1.22 so after updating the path I had to call the _cabal install_ command this way:


```
cabal install cabal-install --constraint="cabal-install < 1.22"
```

The source of this cabal + ghc seems is better described [here](https://github.com/kazu-yamamoto/ghc-mod/wiki/InconsistentCabalVersions#ghc--710-1)

And then I called _leksah_ on the terminal and it worked!

![leksah]({{site.url}}/images/leksah.jpg) 

This is all for today, will update this post with a link to this VM hosted somewhere, as It might be useful to someone.

Comments, questions, feedback as always welcome.