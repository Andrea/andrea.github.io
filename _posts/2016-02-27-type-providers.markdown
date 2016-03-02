---
date: 2016-02-27 23:13:00
layout: post
title: Using Type providers
categories:
- programming
- f sharp
- type provider
---
I wrote a little bit about type providers [here](http://www.roundcrisis.com/2015/02/22/Type-providers/) but I haven't in a while and the
time has come to check them out again.

### The problem

Let's say that I want to use the Giphy API, which gives back data in json format including a (generally funny) gif. From F\# we could take advantage of type providers to avoid a bunch of boiler plate code.

### A concrete solution

1. On an F# script file add a reference to [Fsharp.Data](http://fsharp.github.io/FSharp.Data/) nuget package.
2. In the [Giphy website](http://giphy.com/) you can find the base url and the key to make a request.
3. Use the following code:

```fsharp

type GiphyTP = JsonProvider<"http://api.giphy.com/v1/gifs/search?q=monkey+cat&rating=pg-13&api_key=dc6zaTOxFJmzC">
let baseUrl = "http://api.giphy.com/v1/gifs/search"
let key = // Since Giphy might change the key from time to time, go fetch it off their site

let searchGif searchString =
  let searchTerm = String.map(fun c ->  if (c = ' ' )then '+' else c ) searchString
  let query = ["api_key", key; "q", searchTerm]
  let request = Http.RequestString (baseUrl,  query)
  let giphy = GiphyTP.Parse(request)
  giphy.Data
  |> Array.map( fun x -> Uri(x.Images.DownsizedMedium.Url))

```

One of the results is:

![otter](http://media4.giphy.com/media/slNwi1TTwR40U/giphy.gif)

Which is pretty cool, What happened?


* The `GiphyTP` type is a representation of the data available in the sample, if you inspect the type on an editor, you can see what the compiler has infered information  about the data. When including a url like I have done here, it will go and fetch a sample. The sample can be a live sample (like in the example above), or a local sample (in one or many file(s) or as a live string).

![tp](http://roundcrisis.com/images/2016-02-tp1.png)

* When calling `GiphyTP.Parse(response)` is when a new request to the API is made, the types created at the  are put to use.
* Get data and at this point we could change some of the shape, in this case I return a Uri of one of the possible ones, much more could be done.

If you look at that picture in detail you might wonder, How is it that given a json document, the compiler can give me type information (i.e. Frames, Height  are int, Images is a collection, etc), well, that is  exactly what the type provider is doing, infering the type at runtime so that you don't have to. For each element it will try to
infer first primitive types and then by combining them , more complex types.

As mentioned in the [previous post](http://www.roundcrisis.com/2015/02/22/Type-providers/), the type provider will give you a signature, on demand, as needed by the compiler. At the same time   if we decompile that code you will see something like this.

![dotpeek](http://roundcrisis.com/images/2016-02-tp2.jpg)

and that is because  in the JSon type provider, the types are erased.
A type provider does not necessarily contain any types itself; rather, it is a component for generating descriptions of types, methods and their implementations.

Next, let's see what do type providers look like in other languages.

## Resources

* [Twelve type providers in action](http://blogs.msdn.com/b/dsyme/archive/2013/01/30/twelve-type-providers-in-pictures.aspx)
* [Freeing your Azure data with F# Type Providers](https://blogs.msdn.microsoft.com/mvpawardprogram/2016/01/05/freeing-your-azure-data-with-f-type-providers/)
