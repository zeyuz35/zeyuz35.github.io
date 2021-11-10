
This section mainly collects some results related to breaks in the static factor model literature. To the best of our knowledge, there does not exist any literature which considers breaks in the truly dynamic factor model representation.

Han and Bai provide arguably the most comprehensive literature review on this topic, but their analysis is still limited to static factor models, and also a little unclear at certain points. It does not seem to make any attempt at unifying any results. For example, how earlier work can be retro fit into later frameworks introduced (though this is admittedly not always possible). 

Stock and Watson also note that this literature is very new, and care must be taken care when interpreting these tests. In particular, they are not sure *what* exactly the structural break tests have power against, given the non-identification issue inherent. Additionally, they make a special note that these tests have power against possibly unwanted scenarios, such as drifting parameters. 

These are a lot of questions, but for now, let us focus on: how is the number of estimated factors affected by structural instability (and precisely)?

This questions seems to have been answered when the breaks are in the loadings, but currently it is unclear how breaks in the factors, dynamics of the factors, etc can affect this.

## Stock and Watson

Stock and Watson as part of chapter in a forecasting book (not a "proper" paper) are the first to consider the issue of possible structural instability in DFMs. They do not attempt to derive any theoretical results, and instead show empirically that forecasting performance seems to worsen if one does not account for possible structural breaks.

## Breitung and Eickmeier and Stock and Watson

Stock and Watson propose, without any further theoretical justification, a test for breaks in structural loadings.

Breitung and Eickmeier are first attempt at "formally" approaching structural breaks in loadings. 

Essentially, they formulate a simple hypothesis test for a break in a specific factor loading. They note that pooling these tests is tempting. However, unless the stochastic error term is fully idiosyncratic, then the asymptotic distribution of such a procedure is impossible to work out.

It is for this reason that Han and Bai refer to this as Stock and Watson/Breitung Eickmeier tests, because the methodology is the same.

A simple procedure that is easy to interpret, and arguably the most flexible.

There is no code of this publically available, so a new implementation using R had to be coded up from scratch. An extension to using GLS is pending, but of low priority.

Empirically, an interesting result to note is seemingly different *groups* of variables break at different times. This may be something interesting to note. The most common break dates are 

* insert some empirical results for BE estimator here.

## Chen et al (2014) (CDG)

CDG propose a test for the break in the factor loading matrix by regressing one of the principal components against the remaining components, and conducting a standard time structural break test.

They note that because it is essentially a standard time series structural break regression, theoretically one could consider a more flexible framework. In particular, more sophisticated approaches can be used to test for more exotic forms of structural instability. For example, the authors suggest that Bin and Cheng's non parametric test for smooth changes in time varying parameters could be considered to test for possible smooth changes in the factor loadings, though this is delegated to future research.

## Corradi and Swanson

## 

## Baltagi et al 2017

## Baltagi et al 2020

## Su and Wang (2017)

Su and Wang similarly propose a new framework, and focus on the case for possibly time varying loadings. They model loadings as a smooth function of time and estimate them via local PCA regressions. Their main contribution is a test for time varying loadings based on the estimated squared common component.

Because the existing framework and literature has focused on one time breaks, there should be no easy way to re-concile this with the literature.

Also note that they have a VERY large simulation section, with 10+ (!) DGPs specified.

Hence, these are low priority.

## Su and Wang (2021)

Su and Wang modify their previous contribution in a follow up paper, and propose an easier to understand methodology based on the time varying loadings directly, rather the common components (which is harder to understand).

Similarly, this paper has a very large simulation section, but does seem to be be very similar to their previous paper.
