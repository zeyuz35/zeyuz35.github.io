---
id: ft8FKM7E3SGq5sdSKKc9f
title: Confirmation
desc: ''
updated: 1638935975084
created: 1637022819573
bibliography: [references.bib]
reference-section-title: References
---

## Abstract



## Introduction

Dynamic factor models have been 

## Dynamic Factor Models


The literature in general does not differentiate between the static and dynamic forms for reasons we shall see.



### Dynamic (Static) Factor Models







### Generalized (Truly) Dynamic Factor Models

Any dynamic factor model can be equivalently represented as a static factor model, where the polynomial lags operator is simply 

Estimation of the *generalized* factors is much more difficult.

[@forni_generalized_2000] demonstrate that the dynamic principal components estimator, which is the 

#### Inferential Assumptions



## Structural Breaks in Dynamic Factor Models

## State of the Art Approaches

## Empirical Study

Do an empirical study showing 

### Datasets

We consider 4 four different large empirical macroeconomic datasets.

These are FRED-MD []

## Proposal



## Anticipated Timeline



## Requirements

## References


## Ideas

We are interested in 

1. how many factors are estimated if there are breaks in the factor dynamics
  - autocorrelation parameters
  - breaks in factor innovations
2. how many dynamic factors are estimated if there are breaks in the factor dynamics
3. a procedure to determine the no. of static factors in presence of breaks in factors
4. a procedure to determine the no. of dynamic factors in presence of breaks in factors.

Method:

1. Derive a representation theorem for SFM, when there is a break in factor dynamics (HARD)
2. Using the representation theorem, can simply apply any existing testing procedure, and test for the location of the break (should be easy, just need to verify assumptions)
3. Using representation theorem, prove that existing methods can accurately determine no. of static factors
4. Using representation theorem, prove that existing methods can accurately determine no. of dynamic factors

