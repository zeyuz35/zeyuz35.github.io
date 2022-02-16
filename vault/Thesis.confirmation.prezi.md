---
id: 3RtD305EvXc6EBxOMW4hK
title: Confirmation Presentation
desc: ''
updated: 1644970071254
created: 1637022841285
---

Some general notes for the confirmation presentation

The confirmation presentation (and report) is just a place to convince the panel (Gael) that you have what it takes to successfully complete a PhD.

Note that the presentation itself may be useful to be re-used for actual conference presentations...

The presentation should be a place to sell the idea of the paper, and convince people to actually read the paper later on. It should not be the actual paper.

## Version 1 Draft Notes

Ben said this was good as a base, general structure seems OK

But in general, Ben and Bonsoo say this is quite sloppy (not surprising)

Present a plot or something of structural instability, it's clearer and more convincing as opposed to taking my word at face value

Too much detail in general

Give preview of static DFM equation to start off with (some people are only vaguely familiar with factor models)

Introduce variance parameter

Stress non identification and multiplciative relationship problem

Stress (perhaps new slide) to proposea  methodology to disentangle the breaks

Ensure that the two erros terms are celarly orthogonal

Spend more time on the ERT (this is really hard in general)

Define notation more clearly, $q_1$ in particular is very congusing (Ben thought this was the no. of dynamic factors, not true)

Be consistent with terminiology (sometimes I said factor instead of factor variance)

Methodology (put in extra note that data is usually normalized to 0 1 for PCA)

In general, there are too many slides at the moment

Bonso recommend pesaran paper as additional reference (for continously changing breaks)

tau notation needs to be clearer (separate this into another step)

The procedure is too complicated for most people to follow along, at least on one slide...
### Notes on proofs

DO NOT present the actual proof, just the proposition/result

Unlikely to have working proof done yet, just tell the EXPECTED result

Variance procedure is essentially trying to consistently estimate, and therefore undo the matrix Z0

Therefore, need to show that procedure is consistent for Z0

Bonsoo is available to sit down and work through steps which I am stuck on...


### Technical notes on proof

Bonsoo keeps stressing not to worry about assumptions yet

Do the proof first, then introduce assumptions later to see what is needed to make it work

E.g. long run variance proof for kernel estimation of variance

### Andrews vs Bai and Perron

Andrews critical values allow for up to q = 40, vs BP's q = 10 as a max

They should be asymptotically identical...

Andrews critical values in general are very slightly larger (0.1, 0.2 ish) than BP's. Sometimes BP's are larger.

UDmax and WDmax are always larger, and therefore more conservative

Will need to look into BP paper a bit more clearly, to make sure that this asymptotic relationship is true...


#### Email

While trying to make sense of the empirical results, I've come across some errors and issues, and the solution to them makes the interpretation more nuanced.

Issue:
Baltagi's empirical results (published in their paper) should not be trusted. This is to do specifically with the critical values they used. Their test statistic based on the pseudo factors 2nd moments process, which has a dimensionality of r(r+1)/2. Only empirical data, r can range from 1 to 10, depending on the test used. Bai and Ng's test gives around 7. The issue is that Bai and Perron's critical values need to be applied, for which they only provided critical values for a dimensionality of 10 at most, which is exceeded if r = 5 or more. Bai and Perron provided the critical values in the form of surface response functions (only valid for dimensionality of 10 at most), and this is how Baltagi got their critical values. However, this approach is wrong. 

I am very puzzled, because Baltagi in their paper explicitly say that they explored r value of up to 12 for robustness checks. I suspect one of the co authors who coded it up inadvertendly used the surface response functions without realising that the approach was incorrect. 

This issue does not come up Monte Carlo simulations, because r is kept low (3).

Fix:

The first obvious fix is to swap out Bai and Perron's critical values with those of Andrews (supF). I believe they are asymptotically identical, and the simulated critical values are very close. However, doing this dramatically decreases the power of Baltagi's test to the point where it cannot reject the null for any sample, even the GFC. 

This issue is supported by a remark made in the paper, which states that their estimator loses power when r is overestimates, or underestimated,

The second fix is to simply use a lower estimate of r. Ahn and Horenstein and Onatski have both proposed estimators that, although all theoritically consistent, tend to estimate much lower values of r (around 4 or less). 

New interpretation:

With the fix applied, none of the tests are able to actually reject the Great Moderation Break when the break is treated as a nuisance parameter (to be estimated).

However, when the break date is treated as known, the tests are able to reject it. Han and Inoue did not have an empirical section, but Han's thesis did, and it is in line with that result.

This evidence for a structural break disappears further when we control for factor variance (via our new procedure). The Great Moderation is typically associated with the mid 1980s, 

## Version 2 Notes

## Making Sense of Empirical Data

Original Stock and Watson FA forecasting required stationary factors

However, Bai and Ng 2006 later loosened this, and showed that non stationary factors are still OK
