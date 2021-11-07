---
id: fhf7Gdr3mhOUG1mU5twC6
title: HAC
desc: ''
updated: 1636283478584
created: 1634780245060
---


This document gives a brief overview of Heteroskedasticity and Autocorrelation Consistent covariance matric estimation, and how to implement them.

As the focus is mostly on time series data, there is more of an emphasis on the long run covariance matrix aspect of HAC.

[@stockChapter10Forecasting2006]

## Motivation

Typically, any error terms are assumed to be fully idiosyncratic. That is, each $e_{it}$ is distributed i.i.d. across all cross sectional units and time.

In time series analysis, serial correlation is a common occurrence and can inflate the usual estimated standard errors, making inference invalid/unreliable.

In microeconomics, heterogeneity (cross sectional correlation) is the more common occurrence, similarly this can make estimated standard error inconsistent and subsequent inference unreliable. Note that in the context of OLS, HTSK does make OLS unbiased, but does make its standard errors invalid.

Suppose we are interested in estimating the covariance matrix of a vector of time series, say $X_{it}$, subject to possible serial correlation. Then the correlation matrix via the standard way will result in a likely very dense covariance matrix, which is incorrect.

Additionally, the individual time series may themselves be cross sectionally correlated, adding an additional source of error for covariance matrix estimate.

This is solved via the use of heteroskedasticity and autocorrelation consistent estimators.

In R, this is (and many other covariance matrix estimators) are implemented via the sandwich package.

Note that sandwich implements many advanced features by default, such as using an adaptively choosing bandwidth. This is usually the ``better" way for better finite sample performance, but because this is more subjective, and the literature is lazy and prefers to use a simpler method, they typically do not do this.

## Solution



## Historical

## Implementation via sandwich

sandwich remains the *de facto* standard for implementing HAC. 

Note that sandwich is very cutting edge and automatically implements many newer features in the literature, e.g. automatic bandwidth selection, etc.

This is sometimes too advanced/complex for Monte Carlo studies. Importantly, to replicate the results of some papers, it is sometimes necessary to step down and make it less complicated.

It is possible to specify a fixed bandwidth, etc and replicate the results of a simple, cruder implementation. For an example, see Baltagi et al implementation.


