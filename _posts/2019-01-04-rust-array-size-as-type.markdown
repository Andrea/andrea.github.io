---
author: roundcrisis
comments: true
date: 2019-01-04 10:48:00+00:00
layout: single
classes: wide
title: Rust, array type not generic over the size of an array type.
categories:
- programming languages
- rust
---

## Rust

You can declare and initialise a mutable array in [`Rust`](https://www.rust-lang.org/) like this

```
let mut xs : [u32; 8] = [1,2,3,4,5,6,7,8];
```

alternatively you could separate the  initialisation like:

```
let mut xs : [u32; 8] ;
xs = [1,2,3,4,5,6,7,8];
```

I was surprised when I was not able to re-assign the array with an array of different size... when doing this:

```
let mut xs : [u32; 8] = [1,2,3,4,5,6,7,8];
xs = [2,4];

```
you get this error
```
error[E0308]: mismatched types                                               
  --> src/main.rs:34:10                                                      
   |                                                                         
34 |     xs = [2,4];                                                         
   |          ^^^^^ expected an array with a fixed size of 8 elements, found one with 2 elements
   |                                                                         
   = note: expected type `[u32; 8]`                                          
              found type `[u32; 2]`                                          
                                                                             
error: aborting due to previous error                                        
                                                                             
For more information about this error, try `rustc --explain E0308`. 
```

># error[E0308]: mismatched types

arrays of different sizes are different types. I thought that was really interesting. It is documented

>This limitation on the size N exists because Rust does not yet support code that is generic over the size of an array type. [Foo; 3] and [Bar; 3] are instances of same generic type [T; 3], but [Foo; 3] and [Foo; 5] are entirely different types. As a stopgap, trait implementations are statically generated up to size 32. (from [source](https://doc.rust-lang.org/std/primitive.array.html))



(BTW kudos to the Rust people for very nice error messages)

If one really wants to use a set length array you can still do

```
let mut xs : [u32; 8] = [1,2,3,4,5,6,7,8];
xs[0] = 2;
xs[1] = 4;
```

