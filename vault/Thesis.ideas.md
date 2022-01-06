---
id: vo34RUxa4zvz90eFELX5O
title: Thesis Ideas
desc: ''
updated: 1641432154542
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

This leads to:

    - no change in no. of factors = type 2 break
    - double the no. of factors = type 1 break
    - otherwise, type 3 break

Problem:

This approach seems nice, but has some severe limitations in the presence of type 2a breaks. 

Because both type 2a breaks and type 1 breaks can both affect the no. of pseudo factors, this rank based identification strategy still cannot distinguish between the two. 

Using this rank based test in conjunction with CDG also does not help, because CDG test has power against both type 1 and type 2a breaks, precisely the two cases we which to distinguish from. 

So, all changes in factor dynamics are type 2 breaks that results in no change in factors, but not all type 2 breaks have no change in no. of factors, and not all type 2 breaks are changes in factor dynamics.

### Extra Notes

The existing [@chen_detecting_2014] test already exists, and more or less achieves similar practical results.

This was noted by the literature, but perhaps wasn't quite picked up on why it works, and why this was important?

CDG test still has a hole, which is that it cannot handle (dis)appearing factors by default.

Also, no test has considered the case for breaks in factor dynamics.

Breaks in factor dynamics are presumably from innovations (empirically relevant), but can also arise from
change in AR coefficient
appearance of extra lag

Need to find some shortcoming of CDG test

Shortcoming found. CDG test requires that original factors are stationary, in order for asymptotic distribution to hold. This results in the case of there being both idiosyncratic breaks in loadings, and common breaks in variance, as a case which CDG does not cover, yet arguably is most relevant. This would correspond to type 3 break.

CDG test therefore ONLY has power against type 1 break, has power but test distribution is unknown for type 3 break.

#### Other Notes

The Wald test is much more powerful than the LM test, for structural breaks.

Note exactly too sure why yet.

#### Purpose

Purpose of this paper is to provide a framework which shows clearly how factor dynamics can be misinterpreted as breaks in factor loadings, and a unifying procedure to deal with this.

Factor Dynamic Changes are common, and therefore under this framework, they are classified as so called type 2 breaks in HI framework.

Existing tests which are powerful against this may therefore be erroneously interpreted as changes in loadings, when in fact they are just picking up on variance.

Remarkable to note that CDG's procedure also achieves this, but perhaps they did not realise these implications.

Note that it is not possible to distinguish between a common break in loading and break in factor dynamics, as they are observationally equivalent. 

Goal:

Formally derive and prove the proposed procedure of adjusting the X series directly, and show how this works.

Show that the procedure has correctly identify different types of breaks, and has an asymptotically valid testing procedure in all cases (even if it is piggy backing off previous results)

Type 1: idiosyncratic break in loadings

Type 2a: Disappearance/emergence of new factor

Type 2b: Break in factor dynamics OR common break in loadings (cannot be separately identified)

Type 3: Both of the above occurring at same time

Our procedure should get rid of any possible type 2 breaks in a preliminary step

Other approaches

Using Hansen 2000 JoE, we can use a fixed regressor bootstrap to get around possible non-stationarity in the pseudo factors. 

This could be adapted to the CDG framework, because that test assumes that the factors do not experience any breaks (implicitly, as required by the supWald test application)

This does not seem amenable to the setup as considered by Han and Inoue, however

More accurately, the betas are the pseudo factors as written by Andrews and Bruce Hansen's framework actually correspond to the second moments process of the pseudo factors

This means that if we wish to explore Bruce Hansen's bootstrap approximation, we need to re-jig the code a fair bit...

## End of sample instability tests for dynamic factor models

Extension/adjustment of existing testing procedures to deal with end of sample

This is empirically very relevant, as practically the existing tests cannot get around end of sample trimming at all

Refer to Andrews 2003 for a possible way to do this

This is way harder and not quite good enough - you need to specify the location of the changepoint

Still, may be potentially useful

## Covariance Weighted Forecasting

## DFMs Subject to Threshold Effects

