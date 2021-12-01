---
id: 4GXJm4YpHBWVu5WnZKVm4
title: Hausdorff Critical Region
desc: ''
updated: 1637978717482
created: 1637927430959
---

Hausdorff Critical Region project (simulation work for Don and Xueyan).

## Literature Overview and Motivation

There is a literature that exists called set identification of average treatment effects. This occurs when we loosen our assumptions on a standard treatment effect model, and loose point identification of the ATE, but are still able to identify a "set" of viable ATEs which are compatible. These are also referred to as ATE bounds.

There exist many different ways to actually get these bounds. E.g. SV bounds, Manski bounds, Chesher bounds. We focus on Chesher Bounds, which are one such formulation of the ATE bound.

As a natural consequence, one may be interested in conducting inference on the entire set of ATEs, and produce confidence "intervals", which are now called "confidence regions", to distinguish them. 

There is a literature on producing such confidence regions, the most prominent of which are CLR's half median unbiased estimator.

Chuhui's earlier paper had a finding which discovered that the QMLE RVBP's confidence interval of the ATE (not ATE set), naively used as a confidence region, produced somewhat reasonable results.

This leads us to Don and Xueyan's current paper, which is a bootstrap based approach to calculating the confidence region.

The approach is simple: use a bootstrap to simple calculate the ATE set, and use the quantiles of each of the sets as a confidence region estimate. 

Don is interested in seeing how this performs in the context as a QMLE (ie mis specified) estimator. 

Results:

- works well on gaussian errors
- works reasonably well on skew errors
- works absolutely terribly on log normal errors

Note that this required a LOT of monte carlo simulation, which because this was based on a bootstrap, was very computationally demanding.

A full set of experiments take about a week on MONARCH/my desktop PC/macbook (these are all fairly similar in computational power).

MONARCH is currently in the process of upgrading its compute nodes, will be exciting to see how fast they are!

## Skew normal and log normal

Note that to be a valid error process, these need to be 0 mean, and standardized. Hence, these have a very different parameterization compared to the literature and what is avialable in terms of statistical packages.

Much of this need to be translated from Chuhui's GAUSS code, which was very tortuous.

The Chesher Bound function was ported to Cpp, resulting in a massive speedup.

## Monte Carlo

Be very careful with the Monte Carlo design.

Essentially, we want the design to be "reasonable". All X cells must occur fairly frequently, and need to actually have a large enough effect, but not large enough to drown out the treatment. The treatment itself also has a similar balancing act.

This is very difficult, and if this is ill behaved it WILL show up later on, particularly in the calculation of CLR bounds, which require a derivative calculation.

Finding a reasonable monte carlo design was by and large, a tortuous trial and error exercise, and playing around with the theoretical true ATEs, bounds, etc.

## Numerical Issues

The calculation of the CLR bounds requires the use of a gradient, which is provided numerically. Unfortunately on some more poorly specified simulation designs, the function can be very flat, resulting in a 0 gradient, in turn resulting in something that is undefined.

A numerical gradient is necessary, because the Chesher Bound involves the use of a inf/sup operator.

Note that this inf/sup operator is also a huge bottleneck in the code atm. I can't figure out how to port this, and calculating its derivative in C++, so it is very slow in R.

The HCRs for the log normal errors can also be very ill behaved.

## GitHub

Work is mostly done, and code is on GitHub.

## Plotting

## MONARCH

## Exporting to Excel

Don (and many other less technical people) prefer the format of an Excel spreadsheet.

The easiest way to do this is via the xlsx package, which uses java.

rJava will require a valid installation of both a JRE (for running java) and JDK (for compiling). Make sure you install these!