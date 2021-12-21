---
id: iK1fCibYmGZB28Gm5A09z
title: Empirical Structural Breaks
desc: ''
updated: 1640051653110
created: 1639627979893
bibliography: [references.bib]
reference-section-title: References
---

A collection of breaks that have been detected in the literature. 

This is surprisingly sparse, and each of their methodologies are all arguably dodgy.

Recall that all structural break tests require a trimming of around 10% on each side of the sample, meaning these datasets don't get much to play with.

Also recall that only supremum type test statistics can be used to estimate the actual break date.

Exp and mean type tests require much less trimming (0.02), but cannot be used to yield a break date estimate.

## SW2005

[@stock_implications_2005]'s dataset is considered to be an old, well used dataset in the literature. Comes in monthly format. 1960:2003.

[@breitung_testing_2011] detect a break in 1984:01, with 50-60% of series breaking. Trimming of 10% on either side.

## SW2009

[@stock_forecasting_2021] in their 2009 chapter provide empirical evidence that ignoring structural breaks leads to decreased forecasting performance, and this associated dataset is popular. [@stock_forecasting_2021] themselves focus on 1983 (Great Moderation) as a potential break candidate.

[@chen_detecting_2014] use this quarterly data from 1959:2006, trim 30% on either side (effectively corresponding to 1973 Q3 - 1992 Q3). They seem to conclude that the break date is around 1979, 1980 instead of 1984.

[@baltagi_identification_2017] do not have an empirical study.

[@baltagi_estimating_2021] have an empirical study using this dataset (quarterly) from 1959:2006, trim 10%, and identify

- 1979 Q1
- 1983 Q4

## SW2012

[@stock_disentangling_2012] provides another popular dataset.

This includes some other variables such as instruments (with errors + errata!), but for ouw purposes we only care about the factor model dataset.

[@cheng_shrinkage_2016] use this, but add their own modifications. This is now 1985:2013. They find a break in 2007:2008 ish.

[@bai_estimation_2020] use [@cheng_shrinkage_2016]'s dataset as well, restrict the data to be between 2001:12 and 2013:01 to avoid multiple breaks, and 20% trimming on either side, and find a break date at around 2008:11 - 2009:01. This was the estimator that had terrible Monte Carlo Performance.

## FRED

@barigozzi_simultaneous_2018 uses FREDQD (1960 - 2012) estimates:

1. Common components:
    - 1972
    - 1975
    - 1983
    - 2007
    - 2009

2. Idiosyncratic components:
    - 1972
    - 1974
    - 1983
    - 2007
    - 2008
    - 2010

