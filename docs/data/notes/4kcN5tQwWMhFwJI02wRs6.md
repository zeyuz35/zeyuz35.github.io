
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
