---
id: d8lw1Osg92jmpaCsgK4Tr
title: Structural Breaks
desc: ''
updated: 1638229948918
created: 1636525148960
bibliography: [references.bib]
reference-section-title: References
---

## Bai and Perron


## Perron and Qu

## Qu and Perron


## Single Break Asymptotics

### sup LR

For tests with an unknown break date, a general idea that seems intuitive is to set the test statistic to the best the maximum over a grid of possible break dates.

In the case of an LR test, this will yield a sup LR test statistic, which has a limit distribution corresponding to a tied down Bessel process. 

[@andrews_tests_1993] shows that the sup LM, sup Wald and sup LR are all asymptotically equivalent, and also provides critical values. 

Note that this test has a tradeoff between the trimming on either side. Hence, the range over which we search for the maximum must be small enough to such that the power does not decrease too much (critical values don't increase too much), yet also large enough to actually contain break dates which are potential candidates.

Although the above seems computationally intensive, recall that the optimal break is always the one which minimizes the SSR. For some problems, this then becomes a much easier least squares estimation.

#### P Values by Bruce Hansen

Asymptotic p values (as opposed to critical values, though practically the same) were produce by Bruce Hansen via apoproximating regressions. Bruce Hansen's original GAUSS code was then ported to R, which was then refined by the strucchange package.

As such, the supF, aveF, and expF asymptotic p values are easily accessible.

Unfortunately this was painstakingly implemented by hand from scratch before the Bruce Hansen paper was known to me... This has now been archived, in case there is some strange paper out there which specifically requires the quantiles, and not the p values of this distribution.

### Optimal Tests, exp Wald

[@andrews_optimal_1994] consider tests which are optimal, in the sense that they maximize a weighted average of the local asymptotic power function. 

There are three weighting functions: expWald, meanWald and supWald (from before).

They show that the meanWald test has the highest power for small shifts, whereas the expWald test is better for moderate to large shifts. the supWald test does not technically maximize some local asymptotic power function, though it is admissible (not dominated).

Practically, the preferred tests should be either the supWald or expWald tests, as the meanWald test is severely affected by serial correlation. LM based tests should be avoided.

## Multiple Breaks

[@bai_estimating_1998] extend the previous work on single breaks to multiple breaks. Note that only the supWald test is computationally feasible, and the authors provide an algorithm which will do this efficiently.

Also note that this test requires the pre specification of the number of breaks.

## Double Maximum Tests

Practically, one may not wish to specify a number of breaks to test against.

[@bai_estimating_1998] discuss this issue, and also provide a way to simultaneously estimate and test for breaks, or seqyentially test them.

The limit distribution is this case corresponds to double maximums.

Critical values are provided in the form of surface response regressions.

## Multivariate Systems

[@qu_estimating_2007] extend the analysis of structural breaks to multiple strcutural changes in multiple equation systems. 

They consider:

1. Changes in conditional mean
2. Changes in covariant matrix of errors
3. or both.

These tests are based on normal errors, but can be corrected for serial correlation and HTSK. However, when the tests involves potential changes in the covariance matrix of errors, the limit distributions are only valid assuming normality of errors.

This latter point is perhaps why tests in changes of covariance matrix are not seen too much. 

However, even so, this does allow for things such as testing for changes in the variance of errors, and the framework actually for things such as a change in the mean at a different time as a change in the variance.

Not sure how useful this may be, will need to clean up Qu and Perron code (big task...).