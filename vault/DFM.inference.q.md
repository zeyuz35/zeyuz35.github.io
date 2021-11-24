---
id: U0c40KtWCbQp02iuK28mt
title: q Estimators
desc: ''
updated: 1637727044453
created: 1635335632193
bibliography: [references.bib]
reference-section-title: References
---

Documents summarizing estimator for $q$, the number of *dynamic* factors.

Note that in general, because truly dynamic factors are very difficult to estimate and work with, it is often the case that these methods will rely on a consistent estimator for the static factors $r$ instead. This has the notable advantages of avoiding likelihoods, Kalman filters, etc.

Truly dynamic factor models tend to be very underdeveloped in general. Stock and Watson note in their more recent handbook chapter that there does not exist a comparison between these methods.

## Amengual and Watson (AW07)

[@amengual_consistent_2007] first compute the residuals of the projection of $X_t$ onto the lagged values of the principal components of $F_t$, then apply [@bai_determining_2002]'s IC on the covariance matrix of those residuals. 

## Bai and Ng (2007) BN07

[@bai_determining_2007] work directly with the factor and uise an information criteria to estimate the rank of the residual covariance matrix of a VAR estimated using the r estimated principal components.

There is an implemention in the nowcasting package, which is in the process of being gutted and tailored to our needs.

## Hallin and Liska (2007) HL07

In a completely different approach, [@hallin_determining_2007] propose a frequency domain procedure which uses an IC to estimate the rank of the spectral density of $X_t$.

Note that this was referenced and used in [@ma_estimation_2018], although this was not entirely understood at the time of reading.

Read into [@ma_estimation_2018]'s code again, likely this will contain something related to spectral density!


