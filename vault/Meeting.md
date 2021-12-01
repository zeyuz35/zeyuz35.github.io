---
id: fHzGITjWkNNkiwsQpdex4
title: Meeting
desc: ''
updated: 1638346582929
created: 1634221843124
bibliography: [references.bib]
reference-section-title: References
---
# Meeting Notes

Bring our main focus and try to answer a much more precise question:
what happens to so called consistent estimators of the no. of factors when there is a structural break of some sort?

@stockChapter10Forecasting2006
## Focus Question

How many static factors are estimated by various information criteria in the presence of structural breaks? 

Answer:

The number of factors of as estimated by any consistent estimator is consistent for an equivalent representation of the model, with constant loadings. Such an equivalent representation needs to be given by an equivalent representation theorem, see [@han_tests_2015] or [@baltagi_identification_2017], [@baltagi_estimating_2021]. These are the only representation theorems known to exist.

[@han_tests_2015] and [@baltagi_identification_2017] both have this as propositions, but strangely do not emphasize this. Presumably, this is because representation theorems are not comprehensive enough yet.

Currently, representation theorems handle the cases of breaks in factor loadings quite comprehensively.

Breaks in the intercept of the series can be easily viewed as breaks in the loadings (an intercept is really just a constant factor).

However, a notable gap is what happens when there is a break in the factor dynamics. This is because all of the theory developed thus far has been working within the static factor model framework. That is, the 

This is extra complicated because a break in the loadings cannot be distinguished from a break in the factors.

Note that break in factor dynamics is something I think is empirically relevant - the factors can be interpreted as the primitive shocks which propagate through the economy, in the context of factor models.

Even if one is not inclined to believe in a change in dynamics of the factors, it could be more easily argued that a change in the variance of the idiosyncratic shocks to the factors is believeable, and empirically relevant.


Simulation set up: factor process changes from AR1 to AR2 (made sure it was stationary this time!).

Conjecture: if one can find a way to find the break, then conditional on partitioning the break, the number of factors in each should be consistent.

However, this leads to the problem of testing for such a break.

Simulation shows that existing tests are mixed against this. [@han_tests_2015] has some power, but [@baltagi_identification_2017] does not.

[@bai_determining_2007] provide a representation theorem for how a dynamic factor model can always be written as a static one. However, the actual no. of factors can be ambiguous depending on the what the dynamics precisely are.

New, more precise research question:

- How does the no. of factors change when there is a break in the factor dynamics?
- Simulation results suggest that breaks in factor dynamics tend not to affect the no. of factors estimated 
- how does this reconcile/extend current representation theorems?
- 

Question for supervisors

- How does 

Personal conjectures:

- a change in the loadings has a fundamentally different interpretation, this suggests the change is structural, in the sense that the loadings may have shifted etc
- a change in the loadings can be interpreted as the way that different series responds has changed, but the fundamental structural of the economy itself has not (though this itself is up for debate)
- however, a change in the factor dynamics itself suggests something even more fundamental has changed
- changes in variance are difficult to identify and map with changes in loadings themselves, this could be argued as a mis specification of sorts
- Example: more migration, affects supply shock directly
- new targeted policy, only affects loadings or how people respond to things
- vs a counterexample, such as COVID, which arguably has changed both


## Roadmap

- Show how a change in factor dynamics can be represented as a change in the static factor representation (there was only one mention of this in the literature)
- Show how a change in the factor variance process cannot be represented at present


## Potential Ideas

Hartigan's Chapter 2 directly uses the estimated pseudo factors and tries to estimate Markov Switching on them to disentangle the actual dynamics.

He goes further and tries to do regime dependent factor loadings, but we now know that this methods should be invalid due to a lack of separate identification.




## Empirical Motivation

The number of factors does change on FREDMD. In general, the number of factors has been empirically observed to be increasing over time in various macroeconomic datasets, not just American Data (put in references). This suggests that the breaks have been accumulating over time, resulting in a gradual increase in the number of factors.

Keep in mind that the economics literature tends to identify at most 4 primitive shocks, theoretically and empirically via estimation methods. 


#### Other empirical notes

Weighting the data to get rid of heteroskedasticity somehow does not affect the number of factors.



### Monte Carlo Study Results

Below is summary table of how a DFM can "break" and what effect (if any) this has on the 
number of static factors in a representation. Presumably, any consistent criteria 
will estimate the number of static factors.

Each change has been studied in the context of Monte Carlo simulations. Results 

Change | Effect | Comments | Confirmed in literature?
------------ | ------------- | -------- | ----------------------
Changes in variance of error term | No change | Perhaps unexpected, large changes in idiosyncratic term have no effect on factor estimation | Yes, see [@bates_consistent_2013]
Change in loading matrix | Changes the number of factors | See equivalent representation theorem in  for precise number of factors | Yes, see [@han_tests_2015] or [@baltagi_identification_2017]
Change in individual loadings | Doubles factors | Special case of change in loading matrix - type 1 break (all columns of loadings break idiosyncratically), however, how large this needs to be to affect it is unclear | Yes, but no results on orders
Change in variance of factors | NO change | This doesn't make sense, should be observationally equivalent to change in loadings | Baltagi et al make a comment that this cannot be distinguished from a change in loadings
Change in dynamics of factors | NO change | More work needed, but at present, does not make sense | No work on how to reconcile static with dynamic factors - not sure if necessary if static ones are consistent for dynamic space anyway?


