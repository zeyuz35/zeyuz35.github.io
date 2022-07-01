---
id: micnsf84j1fplkgzjfk34dy
title: Journal
desc: ''
updated: 1656650415501
created: 1656642386743
---

## Story

The most naive and direct evidence that is well documented is simply estimating the no. of
factors over time.

When we consider an expanding window, the no. of factors seems to be increasing, with the 
increases correlated with periods of instability, such as recessionary periods like the GFC.

On the contrary, when we consider a rolling window, the no. of factors seems to be fairly
constant, although this should be taken with a grain of salt given the smaller sample size.

A working hypothesis that seems to intuitively explain what is happening is that
these increase in the no. of factors are simply an accumulation effect of structural breaks
in the factors.

These two exercises are well documented, on the FREDMD by McCracken and Ng, as well as 
other datasets.

There are two broad angles to why people are concerned with structural breaks in DFMs.

## Individual Series

Forecasting - a review chapter by Stock and Watson showed that in sample forecasts
improved when they considered a structural break in 1984 corresponding with the 
Great Moderation. They considered a naive set of Chow (Wald) tests, and showed some
evidence of this.

Augmentation of Factor Space.
The Stock and Watson idea was formalized by Breitung and Eickmeier, who provided
evidence on a series by series level that there were breaks in the factor loadings.

An important observation they made was that if there was a break in the loadings, then
this lead to augmentation of the factor space, which could lead to inefficiency.

## Cross Section

Chen et al and Han and Inoue were the first to generalize this idea of a break to across
the entire cross section, and formulate so called equivalent representation theorems.

At this point, the literature was more concerned with just estimation and testing for 
break dates/fractions, rather than understanding them.

However, a limitation of all of these tests is that they assume strictly stationary factors
for the purposes of identification. Unfortunately, this means that heteroskedasticity in the
factors is interpreted as a rotational break in the loadings, and in general there is no
way to tell rotational changes from orthogonal shifts.

It is not too surprising then, that when we take these tests and run them on empirical data
they simply pick out periods of large changes in heteroskedasticity as a result.

That is, Great Moderation and GFC. Note that these tests can have some trouble on empirical
data not giving enough signal, and because they are essentially Wald tests with r(r+1)/2 dof
they can have some trouble rejecting. However, there is broadly some evidence that GM and 
GFC are picked up as "structural breaks". 

## Disentangling

Our first chapter. 

We argue that rotational breaks and orthogonal shifts are distinctly different, and there is
inherent value in knowing which one has actually ocurred.

Rotational breaks are interpreted as either homogeneous changes affecting ALL series, or, 
arguably the more natural interpretation is that this is simply a change in the factor 
variance. Note that by factor variance, we are referring to the entire variance covariance
matrix, and therefore, in general, is also the result of change in factor dynamics.

Because the theory defines changes in the variance covariance matrix, we shall refer to this
as breaks, but note that most changes in factor dynamics will also induce a break in the 
factor variance.

Rotational breaks are special, because PCA's theory is already consistent for it. As a result,
rotational breaks do not augment the factor space. 

Unfortunately, we do need to assume strictly stationary factors, so this test does also
have power against heteroskedastcity.

On the other hand, orthogonal shifts are shifts in the loadings that are orthogonal to the 
original factor space. If these shifts are large enough that they are of an asymptotically
larger magnitude than the idiosyncratic shocks, then these will manifest themselves as 
augmentations to the factor space, i.e. extra factors as Breitung and Eickmeier were 
concerned about.

### Empirical Result

When I run some working versions of the Z and W test, I can tend to find very significant 
evidence of rotational change (likely just heteroskedasticity), but actually very little
evidence of orthogonal shifts.

The latter point could be argued for or against.

For:
If there is little evidence of orthogonal shifts, this suggests that the shifts are non 
existent/small enough to ignore, or that they are gradual.

The first point is perhaps reassuring to practitioners, as it suggests they are safe to 
ignore.

The latter point is an argument of misspecification, which I will not get into.

Against:
This is essentially an argument against Breitung and Eickmeier, and there will need to be
some explanation of how to reconcile this result. 

The answer is likely because BE test requires consistent estimation of the true factors
in the first step, which if there are orthogonal shifts, is not possible. Strange catch 22
conundrum.

## Next chapters

The overall goal at the end of the day is to provide useful practical advice. 

There are two directions I want to take with this.

## Forecasting

Bai and Ng and Stock and Watson produced very influential papers which formally justified 
the use of estimated factors in say FAVAR or factor augmented forecasting.

As Ben mentioned, this required a lot of assumptions on the true DGP which is highly 
unrealistic, but there is a potential.

Namely, given that there are breaks in the data, and we can isolate their effects into 
rotations and orthogonal shifts, what is the best way to produce forecasts? Can we just
ignore them? 

Maybe they affect only the confidence intervals but not the actual point forecasts?

## Effect of Normalization

I have been brainstorming reasons as to why there is little evidence of orthogonal shifts on
empirical data.

I have narrowed this down to a likely explanation of the standardization process not being 
entirely innocuous.

For background, none of the PCA theory actually requires any strict assumptions on the DGP.

I am speculating, but this is perhaps why on monte carlo, no one ever standardizes the data,
because this is essentially changing the DGP, and the effects of this in conjunction with 
structural breaks added in are unclear.

There is a strong mismatch with applied empirical people and the actual theory.

For example, a relevant question is what happens if there are mean shifts in the X data,
how would this affect structural breaks in DFM?

This is actually too hard to answer at the moment.

Therefore, for now, and definitely for the pruposes of the first chapter, just stay in
line with the established theory, but keep this as a remark.

Conjectures:
The standardisation procedure normalizes all data to be unit variance. This can be viewed as
a GLS like procedure.

How this interacts with orthogonal shifts is unclear, but it is not too much of stretch to
think that this gets rids fo orthogonal shifts, and instead converts them to a rotational one.

This should end up being a reassuring result for practitioners, because it suggests that even
if there are orthogonal shifts, what people have been naively doing all this time is actually
very sensible, and alleviates the issues of augmentated factor spaces in general.



