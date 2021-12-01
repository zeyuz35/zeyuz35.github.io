---
id: cTD6yfaUjMoFn0WeWb2jS
title: Forecasting
desc: ''
updated: 1638255595579
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



### Factor Augmented VAR (FAVAR)

