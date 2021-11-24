---
id: umGHrdI4OaLoU8OOAOdkL
title: Miscellaneous Ideas
desc: ''
updated: 1637724812772
created: 1635337141829
bibliography: [references.bib]
reference-section-title: References
---

Bonsoo says that the pre-treatment of 

$$
X_{it} = \lambda_i' F_t + e_{it}
$$

where $F_t$ itself is allowed to be dynamic. However, the dynamics of $F_t$ do not directly enter the factor structure, and thus this is a called a "static" representation of a dynamic factor model.

Thus, a structural break in $X_{it}$ may occur in the three broad ways:

1. A break in $\lambda_i$
2. A break in $F_t$, which can further be decomposed in
    - A break in the *dynamics* of $F_t$, such as the change in the coefficients of each lag, or the introduction of more lags
    - A break in the error process of $F_t$
3. A break in $e_{it}$
4. A break in the intercept term of $X_{it}$. This is usually omitted from notation, as $X_{it}$ is assumed to be suitably standardised before analysis

Point 4 has not been focused on too much, but this should be a simple case. If $X_{it}$ does indeed contain an intercept term, then this is equivalent to a having an additional factors that is constant across time, and the respective loading changing. Therefore, this break is absorbed as a break in the loadings.

Annoyingly, points 1 and 2 are confusing because due to the multiplicative structure of the DFM, breaks in either the loadings or the factors cannot be separately identified.

The entirety of the frequentist literature is focused on breaks in $\Lambda$, due to the identification issue. This in general is not an issue, because any breaks in the *dynamics* $F_t$ can be equivalently represented as a break in the loadings instead.

To see this, we illustrate some examples:

### Break in the lag coefficient

### Emergence (disappearance) of an extra lag

### Break in lag coefficient + extra lag


The above three cases should cover all possible break sin the *dynamics* of $F_t$.

However, there is a gap in what happens when there is a break in the *error* process of $F_t$. 

This point in particular is important, because [@baltagi_identification_2017] and [@baltagi_estimating_2021] provide the most comprehensive framework in analysing these sort sof structural breaks. Their method is similar to most other methods in the literature thus far, and is essentially analysing the *variance* process of $X_{it}$.

Hence, changing our focus from $X_{it}$ itself to the variance instead, we have.

The variance of $X_{it}$ breaking could be due to:

1. Break in the variance covariance of factors
2. Break in the factor loadings
3. Break in the variance of the error process

However, their method (and many others) cannot distinguish between a break in the factor loadings and a break in the factor variance due to the identification issue, but can distinguish between this and a break in the error variance. 

How it does this is however, is unclear.


## Important Results

[@han_tests_2015] provide a proposition that [@bai_determining_2002]'s IC criteria consistently estimate the number of factors in an equivalent static representation.