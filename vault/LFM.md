---
id: HFuaoX5IEyVutlGQ2fqZx
title: Latent Factor Models
desc: ''
updated: 1639530989632
created: 1639529440635
bibliography: [references.bib]
reference-section-title: References
---

In a separate strand of literature, [@lam_estimation_2011] propose a "Latent Factor Model" (LFM), an alternative formulation of a factor model for high dimensional time series.

The intuition behind this is instead of choosing factor loadings and factors to maximise the in sample variance explained, they now choose to maximize the in sample *covariance* explained. 

Heuristically, this can be said ot be directly more motivated by time series data, which inherently exhibits serial correlation. Interestingly, this has some strange follow on effects, such as serial correlation being required for valid identification of the model.

## No. of Factors

[@lam_factor_2012] in a follow up paper propose a method to estimate the no. of factors consistently.

## Markov Switching

[@liu_regime-switching_2017] provide a method to estimate a markov switching mechanism for factor loadings, within this framework. 

There are some other works that stay within the approximate factor model ([@kim_business_1998], but this used a Kalman filter and Bayesian based approach, and is thus not approximate). 

## Threshold

[@liu_threshold_2020] provide a method to estimate factor loadings subject to threshold switching mechanisms, within this framework.

This is a different framework to the standard approximate factor model, so threshold based breaks have not been tackled yet.

R Code is provided, and an attempt at translating this was done.

### Limitations

Seems that this estimated thresholds don't make too much sense, and the switching happens way too often. The method itself relies on estimates from their previous Markov switching method as a sort of cold start for estimates, which is nherently unstable.

## Changepoints

[@liu_estimating_2022] provide an estimation method for unknown changepoints in factor loadings within this framework. 

Due to the way this framework is different, it is possible to disentangle breaks in the loadings from breaks in the factor dynamics. 

However, given that this is a different factor model entirely, the case for the approximate factor model has not been tackled yet.