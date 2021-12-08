---
id: 1Ad2510r8PbhI7VwhfI8j
title: CWF HAC
desc: ''
updated: 1638767672866
created: 1638746302046
---

Special notes for HAC in CWF model

In sandwich's meatHC(), omega is of the form
omega <- residuals(residuals, diaghat, df)
where residuals are the residuals, diaghat is the diagonal hat matrix
and df is n - ncol of X, the original dataset (degrees of freddom)

The hardest bit here is the calculation of the "hat" matrix
aka the projection matrix
This is the matrix which maps the vector of actual values (response) to fitted values
(sort of like the inverse mapping)
I don't think this is viable for what we are doing, so ignore it for now

The kernel functions are all nicely implemented in sandwich's kweights function,
no need to code these up (phew)
These can be visualized like so below:
kernel = c("Truncated", "Bartlett", "Parzen", "Tukey-Hanning", "Quadratic Spectral")
curve(
  kweights(x, kernel = "Quadratic", normalize = TRUE),
  from = 0, to = 3.2, xlab = "x", ylab = "k(x)")

Forgot all of the above, sandwich has a convenience function lrvar which does all of this
automatically
Some important catches...
lrvar() return the long run covariance matrix of the MEAN of each series
This means that e.g. for an ar(p) with 100 observations, it will estimate
the long run variance of the MEAN, which is divided by the no. of observations
#
Translation: lrvar estimates the variance of the each series' intercept term, after
correcting for any serial correlation and hetereoskedasticity issues
To see this, notice how kernHAC(lm(z ~ 1)) results in the same variance estiamte
as the intercept term for lm(z ~lag(z)) for an AR(1) model

Quite miraculous once you see it in action!
#
Notable issue with this
Because this requires essentially some data for the kernel step, it NEEDS at least a couple of data points
cov() will work for at least two data points
but the kernel estimation needs at least 4, ideally 5 (can't recall the theoretical soruce)

This goes back to the original issue and setup: we need to use rolling/recursive windows
and get estimates of out of sample losses
Because this works directly with the losses (as defined by a loss function), this in
theory should work with a wide variety of setups
e.g. average h ahead forecast loss, optionally asysmterically weighted, etc
Will need to induce assumptions on the losses themselves
Not too sure how this would work with the quadratic methodology later though...

l1 <- rnorm(5)
l2 <- rnorm(5)

cov(cbind(l1, l2))
lrvar(cbind(l1, l2))