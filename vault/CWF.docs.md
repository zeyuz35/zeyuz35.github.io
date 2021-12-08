---
id: vzwbMgEI0SwBP738oki5Z
title: Documentation
desc: ''
updated: 1638746991128
created: 1636095392781
---

Documentation for CWF implementation.

# Goal 
Goal of this project is to implement model averaging, with the weights somehow chosen
via the GMM framework

Motivations
Model selection can be too restrictive - very much all or nothing
Model selection also makes the strong assumption that the correct model is already a
candidate

Model averaging instead does not assume that we the correct model, and aims to produce
a model that is closest to the true model via averaging

There is a vast literature on model averaging, but the results are rather limiting

Bayesian Model Averaging
This is actually a bit easier to work with due to the Bayesian paradigm, but crucially
requires the specification of priors, which goes against the point of the exercise
The paradigm additionally assumes that the "true" model is of the same class
of the models considered - this is unreasonable because the "true" model may be more
complicated that the class we are considering
The difference is nuanced - more general methods focus on one criteria
e.g. MSE, and choose the "best" model (or approximation) according to this
This does not necessarily equate to choosing the "true" model
However, it has been shown in multiple empirical studies to produce better forecasts,
and thus remains popular

Frequentist Model Averaging
This is a much more limited literature
Pre-eminent framework seems to the Hansen's Mallows Model Averaging
However, this framework is quite limited
Candidate models must be nested and linear
The order is which regressors are introduced matters (though this has been subsequently
relaxed)

Frequentist Forecast Model Averaging
Hansen then extends the MMA procedure to producing 1 step ahead forecasts

## Constituent Models

A variety of constituent models have been implemented.


## 
