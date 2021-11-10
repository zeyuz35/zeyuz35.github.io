
## Kalman Filter (state space approaches)



## Principal Components (non-parametric approaches)

## Missing Data

The Kalman Filter can readily handle missing data.

However, this is not the case for PCA.

In the case of PCA, the *de facto* standard in macroeconomics is to mirror that of Stock and Watson, which is an EM algorithm.

Essentially, project any missing data using PCA, calculate the residuals, and repeat until the estimated loadings/factors do not change much.

Note that this is very different to more formal approaches in the broader literature of PCA and missing data - but this seems to be the most widely accepted for missing data and imputation at least in macroeconomics. 