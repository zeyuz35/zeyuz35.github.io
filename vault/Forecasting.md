---
id: cTD6yfaUjMoFn0WeWb2jS
title: Forecasting
desc: ''
updated: 1639532651385
created: 1638254411282
bibliography: [references.bib]
reference-section-title: References
---

## Forecasting

### Factor Augmented Forecasting

This is essnetially some sort of AR(p) or otehr time series model, but with estimated factors added to increase forecasting performance.

[@stock_macroeconomic_2002] famously show that this approach was very good, and it seems to remain popular.

[@bai_forecasting_2008] extend this idea and add some more modern shrinkage methods.

However, the question of how reasonable this is in the context of possible strucutral breaks is unclear.

[@baltagi_estimating_2021] illustrate three possible scenarios:

1. No zero column in loading matrix, and all $\Lambda_0$ and all $\Lambda_\kappa$ are linearly independent - no need to consider breaks
2. No zero column in loading matrix, and all $\Lambda_0$ and all $\Lambda_\kappa$ may be linearly depeneden - need to consider breaks
3.  Zero column in loading matrix - factor nor coefficient identifiable, need to consider for breaks in coefficient

They also remark, rather definitively, that using the entire estimated sample is better, because the full sample estimator of the variables which are not subject to breaks is more accurate. 

I am skeptical fo this, however. 

This last point is similar in spirit to [@corradi_testing_2014], though CS do something a bit different.

[@chen_detecting_2014] provide some simulation evidence. Their simulation setup consists of 2 true factors, but both of their respective factor loadings are subject to an idiosyncratic break (type 1). The number of pseudo factors is therefore $2 \times 2 = 4$. They compare three different strategies:

1. Estimate 2 factors using the whole sample
2. Estimate 2 factors using the whole sample, but zero out the information before the break
3. Estimate the 4 pseudo factors (naively what one would do anyway without knowledge of breaks)

Strategy 1 is shown to be the worst. Strategy 2 and 3 are shown to be similar in performance, but 2 seems to be very slightly better as the break magnitude increases.

In light of this, there does not seem to exist a bias variance tradeoff in general, though more formal research is needed.
### Factor Augmented VAR (FAVAR)

