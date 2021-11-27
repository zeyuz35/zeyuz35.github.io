---
id: cMTEYwmanC2bpnos7diIt
title: R
desc: ''
updated: 1638009657818
created: 1637926289447
---

Some notes for more advanced topics in R.

## S3 Classes

The most basic, and honestly most useful class. Almost everything is done using S3.

Make sure you register custom methods FIRST, then define the method.

## Reference Classes

Don't even bother - just something that R uses internally.

## S4 Classes

The most formal class system of R, but even then this is a huge mess. 

Don't try to actually implement something using this system, too much hassle.

However, it is important to learn how to interface. Use the @ symbol to access items within S4 objects.



```
S4_obj@
```

## R6 Classes

These are the mainstream alternative to S3 for when you want something more advanced.

In general, a pure OOP approach isn't actually that good for most data science related things.

R6 is mostly useful for other applications, such as ggplot (famously). 

Data science workflows tend to benefit more from a functional approach. OOP systems such as R6 encourage less functional approaches, where methods can update objects in place. This is messy, not recommended, and certainly not to my taste.

## General Speed up

Try to vectorise code as much as possible, and use built in functions. Usually many base R functions are directly calling optimized LAPACK or underlying C/C++ code anyway.

A notable exception to this is the tidyverse, which is stubbornly entirely written in R itself.

In terms of data structures, data frames/tibbles are required for tidyverse, which is unfortunate.

But, for other uses, try to stick it either data.table, or matrix (or equivalents such as arrays, xts, etc).

## Paralllelization

Multiple so called backends exist for multicore. The best and most consistent of these is just doFuture, as this is a generalization of other parallel backends.

The enable multifork = TRUE is unstable with GUIs and disabled by default, but in my experience seems stable enough.

Use options to force enable it.

This is by far the easiest way to speed up code.

## Rcpp

When multicore isn't enough, and vectorisation isn't enough, you will unfortunately need to use Rcpp, which involves re-writing slow functions in C++ code. 

Often, these will be linear algebra manipulations. DO NOT use anything other than RcppArmadillo - this is the most full featured and easiest one to work with. It is also well documented.

Re-writing stuff in C++ is very time consuming, and potentially does not have much payoff, depending on the function. Use the R profiler to see where your code is slow, and most of those sections. 

In general, loops, etc are obvious candidates for C++.

## Rcpp Errors on MacOS

Linux plays perfectly with Rcpp, but MacOS is a fucking mess.

Taken from this guide:
https://yiqingxu.org/public/BigSurError.pdf

https://stackoverflow.com/questions/29992066/rcpp-warning-directory-not-found-for-option-l-usr-local-cellar-gfortran-4-8

Also, openMP is finicky and actually requires you to explicitly declare loops to be parallelized. Simply enabling the plugin should not do anything.

The previous point is important because Apple sucks and the clang they ship with macOS has openMP disabled. Apparently there are ways to enable this, but this was messy and i haven't gotten this to work.

Rcpp will love to throw hissy fits about not having gfortran installed. gfortran has not yet been ported to ARM64 yet, so currently just install the intel version and have it work via Rosetta 2. 

Even so, the paths for gfortran are screwed up.

Several conflicting sources, but seemingly the easiest way to is to edit your makevars file:

```
nano ~/.R/Makevars
```

and make it contain the following:

```
CC = gcc 
CXX = g++ 
CXX98 = g++ 
CXX11 = g++ 
CXX14 = g++ 
CXX17 = g++ 
CXX20 = g++ 
CXXCPP = g++ 
FC = gfortran 
F77 = gfortran   
OBJC = gcc 
OBJCXX = g++
FLIBS= -L`gfortran -print-file-name=libgfortran.dylib | xargs dirname`
```

Note that FLIBS will require you to specify which specific path for gfortran explicitly. A workaround for this is provided in the stackexchange link, which directly queries gfortran to get the proper lib path automatically. This should be stable enough even with updates.

Holy hell!

