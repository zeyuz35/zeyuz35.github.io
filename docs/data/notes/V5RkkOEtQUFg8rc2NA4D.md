


To the best of our knowledge, there does not exist any literature which considers breaks in the truly dynamic factor model representation.

## Inference

Suppose that the dynamics of $F_t^0$ change at $T_0$ such that the moment $E(F_t F_t')$ is doubled afterward (variance doubles). Obviously, it is possible to set up an observationally equivalent model where $E(F_t'F_t)$ is constnat over time, but the factor loading matrix is instead scaled by $\sqrt{2}$ after $T_0$. To deal with this, [@chen_detecting_2014], [@cheng_shrinkage_2016], [@han_tests_2015] and [@baltagi_identification_2017] assume the following:

8. Identification condition for structural changes in factor loadings

$$
T^{-1} \sumTfloor F_t F_t' \convp \tau \Sigma_F \\
T^{-1} \sumTfloort F_t F_t' \convp (1 - \tau) \Sigma_F
$$
Note that we have used $\tau$ instead of $\pi$, as some other authors do. 


## Previous Work (need to edit)

Han and Bai provide arguably the most comprehensive literature review on this topic, but their analysis is still limited to static factor models, and also a little unclear at certain points. It does not seem to make any attempt at unifying any results. For example, how earlier work can be retro fit into later frameworks introduced (though this is admittedly not always possible). 

Stock and Watson also note that this literature is very new, and care must be taken care when interpreting these tests. In particular, they are not sure *what* exactly the structural break tests have power against, given the non-identification issue inherent. Additionally, they make a special note that these tests have power against possibly unwanted scenarios, such as drifting parameters. 

These are a lot of questions, but for now, let us focus on: how is the number of estimated factors affected by structural instability (and precisely)?

This questions seems to have been answered when the breaks are in the loadings, but currently it is unclear how breaks in the factors, dynamics of the factors, etc can affect this.

## Stock and Watson

[@stock_dynamic_2011] as part of chapter in a forecasting book (not a "proper" paper) are the first to consider the issue of possible structural instability in DFMs. They do not attempt to derive any theoretical results, and instead show empirically that forecasting performance seems to worsen if one does not account for possible structural breaks.

## Breitung and Eickmeier and Stock and Watson

[@stock_forecasting_2021] propose, without any further theoretical justification, a test for breaks in structural loadings.

[@breitung_testing_2011] are first attempt at "formally" approaching structural breaks in loadings. 

Essentially, they formulate a simple hypothesis test for a break in a specific factor loading. They note that pooling these tests is tempting. However, unless the stochastic error term is fully idiosyncratic, then the asymptotic distribution of such a procedure is impossible to work out.

It is for this reason that Han and Bai refer to this as Stock and Watson/Breitung Eickmeier tests, because the methodology is the same.

A simple procedure that is easy to interpret, and arguably the most flexible.

There is no code of this publically available, so a new implementation using R had to be coded up from scratch. An extension to using GLS is pending, but of low priority.

Empirically, an interesting result to note is seemingly different *groups* of variables break at different times. This may be something interesting to note. The most common break dates are 

* insert some empirical results for BE estimator here.

## Chen et al (2014) (CDG)

[@chen_detecting_2014] propose a test for the break in the factor loading matrix by regressing one of the principal components against the remaining components, and conducting a standard time structural break test.

They note that because it is essentially a standard time series structural break regression, theoretically one could consider a more flexible framework. In particular, more sophisticated approaches can be used to test for more exotic forms of structural instability. For example, the authors suggest that [@chen_testing_2012] non parametric test for smooth changes in time varying parameters could be considered to test for possible smooth changes in the factor loadings, though this is delegated to future research.

Limitations:

- assumes number of factors is constant over time
- test ONLY formulated for changes in loadings ONLY
- but is very easy to implement

## Corradi and Swanson

[@corradi_testing_2014## 

## Baltagi et al 2017

[@baltagi_identification_2017]
## Baltagi et al 2020

[@baltagi_structural_2019]
## Su and Wang (2017)

[@su_time-varying_2017] propose a new framework, and focus on the case for possibly time varying loadings. They model loadings as a smooth function of time and estimate them via local PCA regressions. Their main contribution is a test for time varying loadings based on the estimated squared common component.

Because the existing framework and literature has focused on one time breaks, there should be no easy way to re-concile this with the literature.

Also note that they have a VERY large simulation section, with 10+ (!) DGPs specified.

Hence, these are low priority.

## Su and Wang (2020)

[@su_testing_2020] modify their previous contribution in a follow up paper, and propose an easier to understand methodology based on the time varying loadings directly, rather the common components (which is harder to understand).

Similarly, this paper has a very large simulation section, but does seem to be be very similar to their previous paper.
