---
id: W93wGiYbCqMPzhwsC4cj5
title: Ideas
desc: ''
updated: 1640073987702
created: 1640073650387
---

## Disentangling breaks

Idea is to adjust the data by getting rid of the factor (common) variance somehow

Condition on a break, and calculate the variance of each individual time series

Average over entire cross section

Standardise the data by this common variance

The resulting data should now be free of common changes in variance, and be ready to be used with any standard break test procedure, which is now correctly specified

### Simulation Study

Split the simulation study into cases

1. Null case: no breaks at all

- this is to make sure that the procedure doesn't somehow induce new breaks

2. Idiosyncratic breaks in factor loadings

- this is to make sure that the procedure doesn't somehow screw up the performance of existing tests

3. Common break in factor variance (either via dynamics, or more relebantly, factor innovations)

- this is the main draw of the new procedure, and this should work for this idea to be able to be sold

4. Idiosyncratic break in idiosyncratic shock

- for fun, mainly to see if this has any effect 

5. Common break in idiosyncratic shock

- for fun, but also somewhat relevant, as this could be confused for a shock to factor variance