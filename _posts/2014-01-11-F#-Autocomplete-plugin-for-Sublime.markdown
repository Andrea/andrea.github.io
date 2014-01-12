---
date: 2014-01-11 16:11:00
layout: post
title: F# Autocomplete plugin for Sublime
categories:
- f#
- binding
- python
---

I am learning functional programming and the one I am playing with the most is F#. So I was on the look out for something small to do with the language, the other day I saw a tweet from [@codebeard][codebeard] where he was asking for some help with a plugin for Sublime for F# Autocomplete, what he has is [here][gist].


!
 ![Plugin Preferences]({{ site.images }}/2014-01-11-fsharp-autocomplete-sublime.JPG)

I started to poke around with it to see if I can make it work. So far:

- Find pexpect, I didn't know what pexpect does. According to the github description it's a Python module for controlling interactive programs in a pseudo-terminal
- I needed the FSharpAutocomplete.exe, so I grab the sources and build, I had to get the F#  compiler services package (switch nuget package explorer to pre-release)
- In sublime 3, I had to learn about [packages][package] and how they work  (I always wanted an excuse for this anyway)
- After less than an hour I'm pretty much up and running from a setup point of view (I think) but getting an error when I try to build the package, I think it might be the version of pexpect, though the download page said "Pexpect now requires at least Python 2.6 or 3.2." I have 2.7.5, the error is

    
    *** Error compiling 'C:\\Users\\Andrea\\AppData\\Roaming\\Sublime Text 3\\Packages\\FSharpAutocomplete\\lib\\pexpect-3.0b1\\examples\\astat.py'...
    Traceback (most recent call last):
      File "X/py_compile.py", line 121, in compile
      File "C:\Users\Andrea\AppData\Roaming\Sublime Text 3\Packages\FSharpAutocomplete\lib\pexpect-3.0b1\examples\astat.py", line 39
        print globals()['__doc__']
                    ^
    SyntaxError: invalid syntax

    During handling of the above exception, another exception occurred:

    Traceback (most recent call last):
      File "X/compileall.py", line 115, in compile_file
      File "X/py_compile.py", line 125, in compile
    py_compile.PyCompileError:   File "C:\Users\Andrea\AppData\Roaming\Sublime Text 3\Packages\FSharpAutocomplete\lib\pexpect-3.0b1\examples\astat.py", line 39
        print globals()['__doc__']
                    ^
    SyntaxError: invalid syntax


    During handling of the above exception, another exception occurred:

    Traceback (most recent call last):
      File "package_control.commands.create_package_command in C:\Users\Andrea\AppData\Roaming\Sublime Text 3\Installed Packages\Package Control.sublime-package", line 29, in on_done
      File "package_control.package_manager in C:\Users\Andrea\AppData\Roaming\Sublime Text 3\Installed Packages\Package Control.sublime-package", line 398, in create_package
      File "X/compileall.py", line 61, in compile_dir
      File "X/compileall.py", line 61, in compile_dir
      File "X/compileall.py", line 61, in compile_dir
      File "X/compileall.py", line 56, in compile_dir
      File "X/compileall.py", line 122, in compile_file
    AttributeError: '_LogWriter' object has no attribute 'encoding'

I updated to [python 3.2][python32] and now I'm getting a different error, leaving it here for tonight but will pick it up again as soon as possible.

 


NOTE: There is one thing that I just realized, if I keep this project this way, it will only work in windows and ideally I would like this to be multi-platform. I need to think about ways to mitigate this.



[codebeard]:[https://twitter.com/CodeBeard]
[gist]:[https://gist.github.com/TheRealCodeBeard/8289612]
[package]:[https://sublime.wbond.net/docs/usage]
[python32]:[http://www.python.org/download/releases/3.2/]