---
id: fHzGITjWkNNkiwsQpdex4
title: Meeting
desc: ''
updated: 1638244859674
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



## Roadmap

- Show how a change in factor dynamics can be represented as a change in the static factor representation (there was only one mention of this in the literature)
- Show how a change in the factor variance process cannot be represented at present


## Potential Ideas

Hartigan's Chapter 2 directly uses the estimated pseudo factors and tries to estimate Markov Switching on them to disentangle the actual dynamics.

He goes further and tries to do regime dependent factor loadings, but we now know that this methods should be invalid due to a lack of separate identification.




## Empirical Motivation

The number of factors does change on FREDMD. In general, the number of factors has been empirically observed to be increasing over time in various macroeconomic datasets, not just American Data (put in references). This suggests that the breaks have been accumulating over time, resulting in a gradual increase in the number of factors.

Keep in mind that the economics literature tends to identify at most 4 primitive shocks, theoretically and empirically via estimation methods. 

When partitioned into regimes (either pre conceived or via some break data estimator), 


#### Other empirical notes

Weighting the data to get rid of heteroskedasticity somehow does not affect the number of factors.



### Monte Carlo Study Results

Below is summary table of how a DFM can "break" and what effect (if any) this has on the 
number of static factors in a representation. Presumably, any consistent criteria 
will estimate the number of static factors.

Each change has been studied in the context of Monte Carlo simulations. Results 

Change | Effect | Comments | Confirmed in literature?
------------ | ------------- | -------- | ----------------------
Changes in variance of error term | No change | Perhaps unexpected, large changes in idiosyncratic term have no effect on factor estimation | Yes, see Bates et al
Change in loading matrix | Changes the number of factors | See equivalent representation theorem in  for precise number of factors | Yes, see Han and Inoue or Baltagi et al
Change in individual loadings | Doubles factors | Special case of change in loading matrix - type 1 break (all columns of loadings break idiosyncratically), however, how large this needs to be to affect it is unclear | Yes, but no results on orders
Change in variance of factors | NO change | This doesn't make sense, should be observationally equivalent to change in loadings | Baltagi et al make a comment that this cannot be distinguished from a change in loadings
Change in dynamics of factors | NO change | More work needed, but at present, does not make sense | No work on how to reconcile static with dynamic factors - not sure if necessary if static ones are consistent for dynamic space anyway?


