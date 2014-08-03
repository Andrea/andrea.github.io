---
date: 2014-08-03 14:13:00
layout: post
title: NuGet install tricks
categories:
- programming 
- development
---

Recently I was finishing off the great work [Carsten](http://gettingsharper.de/) started on the Nunit addin for [FsCheck](https://github.com/fsharp/FsCheck) and I had to use a not very common feature of Nuget, running powershell scripts automatically on install.

Disclaimer: I don't like powershell, it is better than nothing, but every time I use is harder that it needs to be.

#### Running powershell scripts automatically when installing and removing packages

There are a few powershell files that run (if they exists on /tools in your package definition): Init.ps1 , install.ps1 and uninstall.ps1
Init.ps1 runs the first time a package is installed in a solution, install.ps1 runs when a package is installed in a project, uninstall.ps1 runs when removing the package. There more information about these files [here](http://docs.nuget.org/docs/creating-packages/creating-and-publishing-a-package) in the section called "Automatically Running PowerShell Scripts During Package Installation and Removal" 

#### The script

In the docs above, when you are looking at what you can do regarding project, it refers you to [this page](http://msdn.microsoft.com/en-us/library/51h9a6ew%28v=VS.80%29.aspx) hint there is no info about Object :/. Thankfully I was pointed towards SpecFlow's install.ps1 file:

https://github.com/techtalk/SpecFlow/blob/master/Installer/NuGetPackages/NUnit.Runners/Install.ps1


I ran into a little problem when building this, I had specified a path wrong on my script and this is the error I got:
