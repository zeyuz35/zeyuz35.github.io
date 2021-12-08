---
id: rVvFqADkXRoSny5lLhog5
title: Cross Validation
desc: ''
updated: 1638413519739
created: 1638413039320
bibliography: [references.bib]
reference-section-title: References
---

## Schemes

### Rolling Window

### Expanding Window

### Cross Validation

This is a naive method, empirically this tends to be mixed. 

Theoretically, it is general not advisable because it destroys any sort of time dependent structure in the time series.

However, there is a famous (and often misunderstood) paper by . 

The result in that paper is quite general. If the data is:

1.  autoregressive and stationary (can be autoregressive non-linearly),
2. the non linear function is *differentiable*, 
3. the residuals from the model are *serially uncorrelated*,

then CV can be shown to be theoretically valid. 

However, the last two points don't tend to hold in practice. 

Many ML models are explicitly non differentiable (e.g. LASSO, elastic net, regression trees).

Also, although testing whether residuals have serial correlation is straightforward via, say, Breusch Pagan, this itself is prone to errors, and also people don't do this in practice.

