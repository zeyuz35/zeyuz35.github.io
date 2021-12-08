---
id: 9k2yfrjFHuORo1it5z5j6
title: New Representation Theorem
desc: ''
updated: 1638945575522
created: 1638938730345
bibliography: [references.bib]
reference-section-title: References
---

## Breaks in Loadings

[@han_tests_2015] and [@baltagi_identification_2017] provide comprehensive so called equivalent representation theorems, which show that any static factor model with a break in the factor loadings can be equivalently represented as an observationally equivalent static factor model with loadings that do not break, but (possibly) extra factors.

Ben, and some others, note that intuitively, breaks in factors are indistinguishable from breaks in loadings. However, almost all papers do not elaborate precisely *how* a break in the factors is translated over. 

[@barigozzi_simultaneous_2018] provides the only paper which tackles this, but this is shoved in their appendix, and in my opinion is not comprehensive enough.

A break confined to the loading matrix is much easier to deal with. Hence, the battle plan is to try to develop a theorem which pushes all breaks into the loadings, then apply the results already derived.

## Breaks in Factor Dynamics

Change of autocorrelation parameter. This is dealt with by [@barigozzi_simultaneous_2018], and more formally tackled here. The more empirically relevant case. This will directly show up as a break in the loadings (proof is trivial).

Addition of factor lags (not too sure how empirically relevant this may be). This can be shown to be the same the as augmentation to the original factors by the space spanned by an extra lag. This is more complicated, because we cannot guarantee that this extra lag is fully linearly independent. In the most general terms however, this can be treated as an addition of an additional factor. No papers have shown this (maybe because it is too easy?).

## Breaks in Factor Innovations

The most empirically relevant one, and the main sell of this idea.

[@stock_chapter_2016] explicitly call out that structural break tests may have some power against breaks in innovations, and needed to be interpreted with caution.

New representation theorem has been formulated and written in notebook. Will need to type up correctly.

Currently, this only works for factor innovations being multiplied by a scalar (I think this is the only relevant case anyway).

If there exists a break in the factor innovations, then the equivalent representation theorem needs to represent the static factors as the lags of factors + innovation process separately, because each factor itself needs to be stationary, and this is the only way to do so.

This necessitates an introduction of 1 extra factor, for each factor innovation break (there can be at most q such breaks, one for each dynamic factor). 

Because the break on this one extra factor is simply a multiplicative one (rotation), this corresponds to a type 2 break on its loading, as classified by the existing representation theorems.

Hence, the overall net effect of such a break is one extra factor being estimated.

The implication of this is that any break in the factor innovations manifests itself as an extra factor (holding all others constant), when estimated via PCA. 

This is now DONE, and should be able to be easily reconciled with the existing frameworks of the literature.

## Practical Issues

How to differentiate between such breaks, and what are the practical implications? The issues is now, breaks in loadings, factors and innovations cannot be distinguished from one another. So even though we can use existing tests and they should have power against the above cases, we do not know which case we are rejecting.

Type 1:

Breaks in loadings which result in linearly independent factors after break. The factors which do undergo this sort of break effectively double in number (this was the case [@breitung_testing_2011] focused on).

Type 2:

Breaks in loadings which result in linearly dependent factors after break. Because of the linear dependency, the factors which undergo this sort of break will NOT augment the factor space and result in extra factors.

Type 3:

From my understanding, this is a technical device, and is simply a combination of Type 1 and Type 2 tests.

Note, there does not appear to be much work done on differentiating between the different types of breaks.

The new equivalent representation theorem is neat, but now I am stuck as to what to do as a next step.

Some other notes:

Although the factor dynamic and innovation breaks have now been shown to be breaks in the loadings as well, recall the mixed evidence from simulation that existing tests had.

Conjecture: these tests don't tend to do too well in finite sample, or perhaps I coded something up wrong?

Idea: 

Try to come up with something that can distinguish and decompose the break into different possibilities. 

This is now easier because we have shown that tests for breaks in the loadings can now be generalized into tests which have power against factor dynamics and innovation breaks as well.

1. Come up with a new test, that ONLY has power against factor innovations

Idea:

Use break estimator to get break (estbalished that they have power against all breaks).

Use estimator of no. of dynamic factors in each regime - this can then be used to tease out appearance of extra dynamic factors

Use estimator static factors in each regime - this corresponds to a type 1 break, which can then be further broken down into:

1. new dynamic factor lag
2. linearly independent change in factor loading
3. change in factor innovations

Using the above result, we now focus on how to differentiate between them, in the case of Type 1 break.

Using [@amengual_consistent_2007]'s framework, get a pro

