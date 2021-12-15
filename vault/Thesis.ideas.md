---
id: vo34RUxa4zvz90eFELX5O
title: Thesis Ideas
desc: ''
updated: 1639540769579
created: 1639441845917
bibliography: [references.bib]
reference-section-title: References
---

## Disentangling Structural Breaks in DFMs

Come up with way to separately identify breaks in factor loadings vs factors, that can be applied to an entire cross section.

Bonsoo & Ben's idea:

Suppose a null hypothesis of no breaks in factor loadings, but breaks in factor dynamics. Then, under this null hypothesis, a break in the variance of each time series can *only* results from breaks in the variance of the factors, or the idiosyncratic shocks.

The main idea come up with a method which gets rid of any possible breaks in factor dynamics, such that existing tests can then be used as a second step procedure to legitimately test against breaks in loadings.

I.e. construct a new X data series with no breaks in the factor dynamics.

Procedure: suppose that a breakpoint in factor dynamics is known somehow (existing tests are consistent for this). Split the sample, and for each series, estimate their variance.

Average out the variance across all series, the idea being that this averaging procedure could sufficiently average out the effects of idiosyncratic shock variance.

Standardize the data across the samples such that any variance from the factor dynamic changes is removed. The result is an adjusted dataset that theoretically has no changes in factor dynamics, and thus fulfills the regularity conditions and assumptions that have been made for existing tests.

Alternative Idea:

When there is a break in the factor dynamics, this will correspond to a type 2 break (in general), and hence this will not result in an extra factors being estimated.

This could form a basis of a disentangling strategy - if the no. of factors before and after the break point are the same, then there is no change in factor loadings.

Problem:
This change is not separately identifiable from type 2 breaks in general. For example, if for some reason the second factor become much more important than the first one after a break consistently across the entire cross section. Additionally, the current type 2 break framework still allows for disappearing/emerging factors.

So, all changes in factor dynamics are type 2 breaks that results in no change in factors, but not all type 2 breaks have no change in no. of factors, and not all type 2 breaks are changes in factor dynamics.

## Covariance Weighted Forecasting

## DFMs Subject to Threshold Effects

