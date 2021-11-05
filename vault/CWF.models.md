---
id: 4b8Oc35b3LgoPjcQsglCx
title: Candidate Models
desc: ''
updated: 1636095708420
created: 1636095674145
---

We detail our candidate models we consider. Most of these models are taken from the survey of inflation forecasting. The models are detailed below broadly from simplest to most complex.

## Univariate Models

Random Walk Model

Auto-Regressive (AR) Model

Fixed Rho (fixed coefficient) Auto-Regressive Model

Auto Regressive Integrated Moving Average (ARIMA) Model
Stock and Watson note that IMA (1, 1), which is a ARIMA (0, 1, 1) model is good for forecasting inflation.

Phillips Curve and other Economically Motivated Models



## Multivariate (Factor) Models

There exists a large literature on the benefits of factor augmented (FA) forecasts. Factor augmentation relies on the underlying assumption that the broad macroeconomy admits a "factor-structure" of the form
\begin{align}
X_t = F \Lambda' + e
\end{align}
where $X_t$ is a $T \times N$ matrix of macroeconomic time series, $F = (F_1, \dots, F_T)'$ is $T \times r$ matrix of time varying factor series, $\Lambda = (\lambda_i, \dots, \lambda_N)'$ is a $N \times r$ matrix of time invariant factor loadings for each series, $e$ is the error matrix, and importantly $r < N$, i.e. $X_t$ can be represented with a lower number of factors. 

Note that although $F_t$ itself can be a dynamic vector process and $\lambda_i$ can corresponding to a "dynamic factor model," a dynamic factor can always be represented with an equivalent "static" representation, and as such for most practical purposes (including forecasting), the model is treated and estimated as a static one.

Estimation of dynamic factor models is typically via the use of principal components (eigen) analysis, as this has been shown to consistently estimate the factors and loadings. Note however that because neither the factors nor the loadings are separately identifiable, estimation is only "consistent" in the sense of consistently recovering the column space spanned by the true factors and corresponding loadings. 

Estimation of the number of factors $r$ is done either informally via graphical tools such as scree plots, or more formally using information criteria which have been shown to be consistent in selecting $r$ (see ).

Once the factors themselves have been estimated, they can be used as extra external regressors to "augment" forecasts. 

Factor Augmented ARIMA


Principal Components Squared

Estimate PCs as usual on $X_t$, then construct $\widehat{F}_t, \widehat{F}_t^2$. Principal components squared allows for the volatility of the factors to have predictive power. 

Squared/Quadratic PCA

This is PCA but estimated using $X_t^* = \{X_t, X_t^2 \}$. Quadratic PCA is a superset of this method and also includes all cross terms between all $X_t$ series, but it has been noted that this is very computationally demanding and adds little predictive performance. This is more advanced that Principal Components Squared, because it allows for the factors themselves to be non-linear functions of $X_t$.

Targeted Selection of Predictors

Note that although the number of factors $r$ can be determined using information criterion, this does not always translate to the optimal number of factors to be used in forecasting. Bai and Ng therefore propose the use of soft thresholding via Least Angle Regressions (LARS) in order to decide on how many predictors to include for augmenting forecasting regressions.

In particularm, they consider LA(5) = vector fo 5 best predictors selected by LARS, LA(PC) = factors estimated from 30 best predictors as selected by LARS, LA(K*) = vector of k* best predictors selected by LARS, and LA(SPC) = factors estimated from the 30 best predictors in $X_t, X_t^2$ as selected by LARS.

Other Models

There are many other models available for forecasting (such as other forms of model averaging, Bayesian forecasting methods, etc) but for simplicity these are not considered at this stage.
