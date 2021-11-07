---
id: SKUZ6b0dCeZkJQWeJkLAZ
title: Structural Break P Values
desc: ''
updated: 1636284316460
created: 1635212376940
---

## Andrews critical Values

## Andrews asymptotic p-values, by Bruce Hansen

Asymptotic p values (as opposed to critical values, though practically the same) were produce by Bruce Hansen via apoproximating regressions. Bruce Hansen's original GAUSS code was then ported to R, which was then refined by the strucchange package.

As such, the supF, aveF, and expF asymptotic p values are easily accessible.

Unfortunately this was painstakingly implemented by hand from scratch before the Bruce Hansen paper was known to me... This has now been archived, in case there is some strange paper out there which specifically requires the quantiles, and not the p values of this distribution.

## Bai and Perron

The main results that are used a lot in structural break analysis for time series.

Essentially, this amounts to finding the break point such that the total sum of squared residuals from both partitions is minimized. This is implemented in the very old strucchange package, and interfacing with it is very tedious. Therefore, some wrapper functions had to be introduced.

Note that it is impractical to re-implement this, as Bai and Perron came up with a specific algorithm which computes this minimization problem very efficiently.

Note that because these are supremum type statistics, the critical values are non standard and need to be simulated, which is computationally demanding.

In subsequent follow up, Bai and Perron provide simulated critical values in the form of surface response regressions/functions. Essentially, for space considerations they fit an almost perfectly fit regression to the critical values so that people can easily generate them in the future, and this is the implementation used.

## Qu and Perron

The multivariate/multi-equation extension to Bai and Perron. 

This is much more complicated and to my knowledge does not seem much use in the literature, simply because it is difficult to think of any realistic models such that this test would actually be needed/wanted.

Notably, there is no easily accessible implementation of this, and only Qu's GAUSS code which is terrible.

A conversion project for this ongoing, but of very low priority.



