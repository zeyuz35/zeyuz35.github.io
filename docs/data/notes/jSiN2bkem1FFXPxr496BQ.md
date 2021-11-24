# SFM Functions

Documentation for SFM implementation using R.

All SFM will return an object of class "DFM", mainly for legacy reasons. In the future, 

The main constructor function is DFM, and by default this will estimate a *static* factor model via principal components.

## SFM.fit

Internal fitting function for fitting static factor models, aka PC estimators.

## vcov

The main draw of this function - there does seem to be any easily accessible implementation of variance covariance matrix estimation of any of the factors, loadings etc despite the results having been derived a long time ago.

This is not that useful for inference, however, many subsequent papers rely on some transformation of the varaince covariance matrix (e.g. Su and Wang papers), so it is very helpful if these are available.

These can be used to construct confidence intervals for the factors and loadings themselves, but this is less useful because the dimensionality is too high, and they tend to be very wide anyway.

More useful is the ability to construct confidence intervals for the "fitted values" or estimated common components.

## fitted

Returns the "fitted values", or more commonly known as the common components.

## resid

Residuals.

## 
## 
