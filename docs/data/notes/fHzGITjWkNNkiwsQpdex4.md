# Meeting Notes

Bring our main focus and try to answer a much more precise question:
what happens to so called consistent estimators of the no. of factors when
there is a structural break of some some?

@stockChapter10Forecasting2006
## Focus Question

How many static factors are estimated by various information criteria in the presence of structural breaks? 

## Roadmap

A collection of unanswered questions which may have potential.

It is currently known that the most innovative and latest break fraction/points estimator rely on the second moments matrix of the pseudo factors. Unfortuntely this method cannot distinguish between a break in the factor variance and the factor loadings, because of a non-identification issue.

Currently, everything is estimated and done via the static model setup. It is arguable that this is all that is necessary, but to date no attempt has been made to reconcile this with the dynamic factor model literature (this is quite difficult). 

As an easy path into doing something for this, derive some results and show how breaks in dynamic factors can be represented as breaks in equivalent static factors? (don't seem too hard and hasn't been done so far).

## Answers

Existing information criteria are consistent for the number of static factors, under the assumption of no structural breaks at all (no breaks in loadings or factors). The conjecture (and what seems to be correct so far) is that existing methods will consistently estimate the number of factors, as given by equivalent representation, such that there are no structural breaks in the factors/factor loadings.

However, finding such an equivalent representation has not been fully explored yet.

BKW and HI formulate an equivalent representation theorem, which can precisely answer and 
reformulate breaks in the factor loading matrix as (potentially) extra factors. 

However, this is looking at breaks in the entire loading matrix itself.

Also, this does not address how breaks in the factor dynamics or factor variance can affect
the number of factors estimated.

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


