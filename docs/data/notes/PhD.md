
Welcome to my website!

This website has been built using Dendron, and each topic has been collated into collapsible sections on the left hand side. Below is supposed to be a graph view so that you can visualize and explore how topics are connected to one another, but this has not been implemented yet.

The search functionality is very powerful. Note that default search tries to exact match actual page names - make sure to prefix with ? to get actual search.

## Latest Meeting Agenda

Main points:

- 


Ideas for new test statistic:

Question:

How many *static* factors are there subject to breaks?

- This is mostly answered, IC are consistent for an equivalent *static* representation without breaks (proposition in [@han_tests_2015], and a comment in [@baltagi_estimating_2021])
    - These are not that easy to work with, but this covers almost all cases of breaks
    - A direct implication of this is that structural breaks will *always increase* the no. of static factors estimated
- However, representation theorems have not considered any breaks in factors that cannot be explained by a change in loadings, due to the multiplicative structure
    - change in variance of primitive shocks (heteroskedasticity)
    - mean shift in factor process

Does overestimation/underestimation actually affect subsequent forecasting?
- This is a good opportunity to tie in with
    - Machine Learning thesis (this was essentially forecasting), demonstrating one way which ML methods can break down
    - CWF project, which ideally could offer a possible solution to this (or at least provide a method that is more robust to breaks)

- Test for structural change one time, vs smooth changes (non parametrics), kink vs curve
- Test for change in variance of primitive shock innovations (this does not seem to be covered yet)
- Test for changes in factor dynamics, based on the assumption that the number of primitive factors does not change (seems reasonable enough in economics...?)

Housekeeping

- macroXTS class is finished
- static $r$ IC have been implemented
- standard PCA estimator should be fully implemented
- dynamic $q$ IC are all WIP
- other estimators of DFMs are not yet implemented
    - EM estimator (viewed as QMLE)
    - Bayesian (can of worms)
    - Spectral density estimator (useful for getting the actual primitive shocks)

## Quick Links

[[roadmap]]

[[Meeting]]

[[TODO]]

[[Misc]]