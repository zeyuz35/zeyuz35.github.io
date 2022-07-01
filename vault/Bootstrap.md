---
id: gzk1vij76zsh0gqh2e9shs1
title: Bootstrap
desc: ''
updated: 1651802017905
created: 1651800199898
---

The Bootstrap is a general procedure that can be used to get an empirical distribution of anything.

## Residual Bootstrap

This is the easiest one to implement.

Simple get the "fitted values" of something but with the null hypothesis imposed.

Then, generate new "bootstrap" samples by resampling the residuals. 

## iid

Standard bootstrap, only suitable for iid errors

## Wild Bootstrap

Perturb the residuals by multiplying them with a RV with mean 0, var 1 variable. This is suitable for cross sectional correlation.

In the case of panel errors, it is reasonable to to do this with entire slices of cross sectional units

## Block Bootstrap

Organise the data into different time series blocks, then shuffle the blocks

This is suitable for preserving stationarity

Can easily be extended to panel, but making the block slices across the T dimension

## Dependent Wild Bootstrap

A combination of the two, for when there is both cross sectional and serial correlation

Essentially, generate a wild multiplier that is mean 0 and variance 1, but with some amount of serial correlation

E.g. AR(1). Presumably, this will need to be calibrated somewhat to emulate the true DGP

Then, block bootstrap the wild multiplier

Then, multiply them

Unfortunately, according to Bonsoo, this does not usually work well in practice

So, try to avoid this if we can

## Practical Implementation

No easily accessible implementations exist, particularly for an entire panel of errors

So these have been coded up from scratch, with a new bootstrap framework

tsboot and boot try to simplify things way too much, and it is very difficult to look into individual bootstrap samples, which is desirable

Remember to actually check whether serial/cross sectional correlation present in the actual residuals first! Avoid any unnecessary work




