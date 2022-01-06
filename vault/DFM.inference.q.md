---
id: U0c40KtWCbQp02iuK28mt
title: q Estimators
desc: ''
updated: 1640053027200
created: 1635335632193
bibliography: [references.bib]
reference-section-title: References
---

Documents summarizing estimator for $q$, the number of *dynamic* factors.

Note that in general, because truly dynamic factors are very difficult to estimate and work with, it is often the case that these methods will rely on a consistent estimator for the static factors $r$ instead. This has the notable advantages of avoiding likelihoods, Kalman filters, etc.

Truly dynamic factor models tend to be very underdeveloped in general. Stock and Watson note in their more recent handbook chapter that there does not exist a comparison between these methods.

## Stock and Watson 2005

[@stock_implications_2005] propose the first procedure, which is a modified version of BNIC. However, they did not study the consistency properties of this, and such properties are worked out by [@amengual_consistent_2007].
## Amengual and Watson (AW07)

[@amengual_consistent_2007] first compute the residuals of the projection of $X_t$ onto the lagged values of the principal components of $F_t$, then apply [@bai_determining_2002]'s IC on the covariance matrix of those residuals. 

There is some MATLAB code, which needs to be translated to R. 

The procedure itself seems very simple though...

As far as I can tell, the same assumptions as [@bai_determining_2002] are used. That is, factors are assumed to be stationary.

High level overview:

1. Re-parameterize the model, such that Y = X - lags of Ft. Y therefore corresponds to a factor model with $q$ factors, which correspond to the unobserved factors
2. Y itself then can be expressed as a static factor model, with q factors, and the factors themselves corresponding to the factor innovations
3. For the above to work, you need to construct an accurate enough estimator for the Y, which in turn requires an accurate estimator for the factors (and their lags)

Note that the assumptions that underlie this requires that the Y parameterization to satisfy the BNIC assumptions, because we are essentially running BNIC on Y instead.

Note that also, in order to get an accurate estimate of the loadings and factors, standard BN assumptions also need to be satisfied by the original static factor model representation.

Therefore, Y itself needs to satisfy the BN assumptions, and the estimators of F, Lambda, Phi and/or Pi are sufficiently accurate.

The latter point is usually not a big deal, because under standard VAR assumptions, the VAR estimator (via OLS) is consistent for Phi and/or Pi. Even the optimal lag order (p) to be used can be estimated consistenly via BIC.

This sort of brings us to the original problem: come up with an equivalent representation theorem for breaks int he facotr dynamics.

## Bai and Ng (2007) BN07

[@bai_determining_2007] work directly with the factor and use an information criteria to estimate the rank of the residual covariance matrix of a VAR estimated using the r estimated principal components.

There is an implementation in the nowcasting package, which is in the process of being gutted and tailored to our needs.

The nowcasting package has a working implementation of this that we can use directly.

High level overview:

1. Estimate the *static* factors (including use of BNIC to get consistent estimate of factors), which will consistently span the space of, and therefore can be used as an estimator, for the space spanned by the dynamic factors
2. Then, estimate a VAR(p) in the estimated factors
3. Use the estimated residuals for the VAR
4. By a lemma, the estimated residuals can be used to yield a consistent estimate of the covariance matrix of the true innovations
5. Apply a matrix rank testing procedure to determine the rank of the var covariance matrix (they provide two new ones due to some technicalities)

### Limitations

Covariance matrix of static factors are same (slightly adjusted) version of [@bai_determining_2002], which requires stationary factor processes





## Hallin and Liska (2007) HL07

In a completely different approach, [@hallin_determining_2007] propose a frequency domain procedure which uses an IC to estimate the rank of the spectral density of $X_t$.

Note that this was referenced and used in [@ma_estimation_2018], although this was not entirely understood at the time of reading.

Read into [@ma_estimation_2018]'s code again, likely this will contain something related to spectral density!

[@barigozzi_simultaneous_2018] has some MATLAB code, but needs to be translated to R.

A stopgap solution is using the POET package which is something unrelated, but has the HL estiamtor implemented.

High level overview:

1. 