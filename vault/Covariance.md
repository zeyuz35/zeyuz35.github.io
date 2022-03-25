---
id: reqaa2uynsb1m5bebffsl9l
title: Covariance Matrices
desc: ''
updated: 1647844741189
created: 1647837933120
---

# Review of High dimensional Covariance Matrix Estimation

Review of high dimensional covariance matrix literature, likely to be required/exploited for CWF project.

CWF is meant to be a way to weight forecasts with the inverse of the covariance matrix of residuals.

Bonsoo ideally wants to allow this to be theoretically infinite in dimensions (large N), in addition to large T.

The way I see it, the main novel ideas are:

1. Weighting forecast methods by the covariance matrix of residuals directly

- Most existing methods only weight by each methods' squared loss or something similar, and 
this should be identical to weighting by just the *trace* of the covariance matrix

2. Allowing theoretically infinite models (large N setting)

3. Possible allow for structural breaks/changes in the covariance matrix itself (this seems to be pervasive)

Empirical target(s):

- Inflation
- Output
- Unemployment

Inflation and Output (GDP) forecasts have the largest literature, and easiest to justify

Pretend that each i is now a forecasting method, and t is its relevant forecast

# Review (Bai and Shi)

There is a special emphasis on the inverse of the matrix as well, but this seems to be more
focused on finance

Maybe we could co opt something else from Finance? Need to spend more time on that associated literature review

4 Methods

1. Shrinkage

This is not quite LASSO/Ridge etc. It's more akin to a James Stein sort of estimator, where
you try to weight the matrix between the sample covariance, and one implied by a model

See Ledoit and Wold for details

2. Factor Models (!)

Observable Factor Models

Given some known factors, the covariance matrix can be derived... Fan et al paper focuses on this

Latent Factor Models (don't get confused!)

Bai here is referring to standard PCA estimator.

Lambda' Lambda + var(ep) is consistent for the covariance matrix

var(ep) is the hard part

This doesn't really say how we can then take the inverse of the N x N matrix, which is 
possibly very large

3. Bayesian and Empirical Bayes



4. Random Matrix Theory

When T is much smaller than N, the sample covariance matrix has a lot of noise



# Review (Clifford Lam)

Very large review that is likely not that useful...

However, apparently there does not estimate a formal method which aims to estimate ||w - what||
in the context of say, portfolio optimization

This could be precisely our new contribution, because our GMM framework aims to consistently
estimate these weights

In this view however, w cannot be infinite dimensional

