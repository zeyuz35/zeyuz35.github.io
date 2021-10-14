---
id: CQTUwoXQNcd0Y7la7IaAn
title: Appendix
desc: ''
updated: 1634214733718
created: 1634214393225
---
# Appendix

This appendix document includes general results that are broadly applicable, and other 
details that are otherwise too messy to include in the main body of the review.

## Long Run Covariance Matrices

In the context of time dependent data, serial correlation is a common occurrence and can inflate the usual estimated standard errors, making inference invalid/unreliable. 

More precisely, serial correlation is when the innovations (error) terms in a stochastic process are themselves serially correlated. 

Suppose we are interested in estimating the covariance matrix of a vector of time series, say $X_{it}$, subject to possible serial correlation. Then the correlation matrix via the standard way will result in a likely very dense covariance matrix, which is incorrect. 

Additionally, the individual time series may themselves be cross sectionally correlated, adding an additional source of error for covariance matrix estimate.

This is solved via the use of heteroskedasticity and autocorrelation consistent estimators. 

In R, this is (and many other covariance matrix estimators) are implemented via the sandwich package.

Note that sandwich implements many advanced features by default, such as using an adaptively choosing bandwidth. This is usually the ``better" way for better finite sample performance, but because this is more subjective, and the literature is lazy and prefers to use a simpler method, they typically do not do this.

lrvar() and kernHAC() have extra arguments to facilitate a more DIY approach, and this is critical for replicating the results of various papers.

```{r}
library(sandwich)
# Simulate some AR1 mts
X <- data.frame(
  x1 = arima.sim(list(ar = 0.5), n = 100),
  x2 = arima.sim(list(ar = 0.5), n = 100),
  x3 = arima.sim(list(ar = 0.5), n = 100)
) |> as.matrix()

# Usual variance matrix (incorrect in presence of serial/cross sectional correlation)
X |> var()

# using lrvar (can take a while to run), by default an Andrews type
X |> lrvar()

# lrvar is that same as regressing ALL columns on a constant, then applying
# an appropriate HAC mthod to it
# This may be preferred if you wish to work with an lm() object environment
lm(X ~ 1) |> kernHAC()

# Newey West Type (prewhtie and adjust = TRUE by default)
X |> lrvar("Newey-West")

# Using lm interface
lm(X ~ 1) |> NeweyWest(prewhite = TRUE, adjust = TRUE)

# Specifying arguments, such as bandwdith
X |> lrvar(bw = 0.15)
```



