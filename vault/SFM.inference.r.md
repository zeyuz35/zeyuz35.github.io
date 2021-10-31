---
id: wQruEPvAQOC2xbS48WvgQ
title: r Estimators
desc: ''
updated: 1635497448771
created: 1635206494435
bibliography: [references.bib]
---

A summary for estimators of $r$, the number of static factors.

## Bai and Ng

The most famous and widely used estimator. 

## Onatski (2009) ON09

Onatski derives hypothesis tests regarding the number of static and/or dynamic factors in a DFM context, related to the empirical distribution of eigenvalues.

Note that this is a specific hypothesis test, so it difficult to use in a practical sense. I.e. why set up the null hypothesis to test for a specific number of factors?

MATLAB code is available from his website. However, this isn't too useful (for now), so conversion to R is on hold.

## Onatski (2010) ON10

Related follow up, Onatski produces an actual method to determine the number of *factors*. Need to investigate if this refers to static or dynamic factors.

Esitmate r as the largest value of $k$ for which the different between the $k$ and $k + 1$ eigenvalues of the covariance matrix exceeds a threshold.

Implementation converted to R from Onatski's MATLAB code.

Note that this is essentially runs sequential tests for the number of factors in a DFM, and therefore only results in an estimate. There is no corresponding plot function for this, accordingly.

## Ahn and Horenstein 2013 (AHER, AHGR)

Ahn and Horenstein derive an alternative estiamtor for r based on the behaviour of how the eigenvalues change/grow. 

This is basically a fancier scree plot.


