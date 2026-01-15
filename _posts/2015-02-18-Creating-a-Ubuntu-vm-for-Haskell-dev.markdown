---
date: 2015-02-19 11:44:00
layout: single
classes: wide
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

## Another Day, another pain

couldnt install glfw easily so I decided to create a new vm :|

* New vm was easy, got ubuntu 14.10 because it had glfw package (it seemed easier to do this than to build from source, if you want to do this, there is a lenghty explanation [here]())
* First thing I did was instal libglfw and it seemed to work
* My resolution was 640x480, not fun -> resolution problem http://www.linuxbsdos.com/2014/10/31/solutions-for-low-screen-resolution-in-ubuntu-14-0414-10-and-virtualbox/
* glfw installed yay!

```
sudo apt-get install libglfw3
```

It would have been cool to have a some sort of way to know that the installation worked

* for FTGL I had to use 

```
sudo apt-get install libftgl2 

```
It did work

* Installed leksah 
* Ran leksah and ran the welcome and I get a message "cabal does not exist", not sure what to do here
* Installed sublime and SublimeREPL and this just worked, at this point I wanted to get something working

* Build the code I got from the [repo](https://github.com/elisehuard/game-in-haskell) and it failed with cabal dependencies because I had an old version of ghc, the way to solve the problem is [here](https://github.com/elisehuard/game-in-haskell/issues/2) so, the good news is that there is a reliable source to where to get binaries :D 

After doing this I was able to build the project however I can only run a few of the projects, some fail requesting that I enable 3d acceleration, however when I do this, the vm doesn't work well.

* Many people have mentioned [Halcyon](https://halcyon.sh/) it's a way to handle dependencies in Haskell projects in a saner way. My understanding is that it doesn't require cabal or ghc to start, builds from source and keeps the binaries you need somewhere for you so that you have the same setup every time and you can share this with anyone that is working on that project. I think my understanding of this is a little incomplete so I recommend you have a look at it if you are interested. 


my feelings exactly:

<blockquote class="twitter-tweet" lang="en"><p>escaping cabal hell is like untangling a ball of yarn <a href="http://t.co/7EEnAQPxWR">pic.twitter.com/7EEnAQPxWR</a></p>&mdash; Kat Chuang, PhD (@katychuang) <a href="https://twitter.com/katychuang/status/563891948013223937">February 7, 2015</a></blockquote>

Comments, questions, feedback as always welcome.

