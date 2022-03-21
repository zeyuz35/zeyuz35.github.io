---
id: 3CJuINQspPvgBEeXkWbrU
title: Disentangle
desc: ''
updated: 1647301193411
created: 1643941577338
---

PCA is consistent for time invariant loadings, and non stationary factors.

Stock and Watson originally developed forecasting theory which required stationary factors

But Bai and Ng later on loosened this theory to be consistent with the PCA assumptions

Therefore, from an applied perspective, time varying loadings are problematic as this augments the factor space, whereas time invariant factors are not, as they do not augment the factor space

Note that there is the special case of integrated factors/series, but this is a whole different literature

It was using this logic that practitioners arguably should not care about Type 1 Breaks

This led to the current proposed procedure:

Idea: adjust the data so that type 2 breaks do not exist anymore, then re run the existing estimator

Procedure:

Partition data
estimate no. of factors in each
Choose the lower no. of factors
Project/get the fitted values for each dataset, using the lower no. of factors
Based on the projection, calculate the variance of each series
Average the variance of each series
This average variance is an estimate of underlying factor variance

It seems to work well on simulated data, and seems to make some sense on empirical data

However, now Bonsoo says that this is not quite enough, and true break disentanglement is needed

Idea: Similar to before, adjust the data so that type 1 breaks do not exist in the data, and only type 2 breaks do

Procedure Ideas:

## Issues

### Singular covariance matrices for psuedo second moments processes

The factor adjust procedure can remove too much noise and result in an adjusted dataset that is "too perfect". This results in PCA producing close to a perfect fit, and is most obvious when using type 2 adjustment on type 1 breaks. 

HI is able to circumvent this by swapping out solve() to ginv() which tends to handle near singular matrices better. BKW actually needs lrvar() to be able to work on the pseudo second moments. 

Solution: add on the original estimated noise from naive dfm projection, does not seem to affect results, and fixes this strange issue.

The loading adjust procedure similarly can sometimes do this. Similar solution where adding on the original estimated noise seems to solve this.

Note that this issue tends to only appear on data that is too perfect, i.e. simulations. Empirical data does not tend to have this issue.

### Parts of Proof

Need to show that the factor variance procedure is consistent for the Z matrix

This is confirmed numerically in Monte Carlo

Specifically, the eigenvalues of the Vnt matrix of each subsample are consistent for the eigenvalues of the Z matrix...

Need to show that Type 1 break does not translate over to the eigenvalues in a meaningful way

## Empirical Results

The results are definitely not as robust as they could be. In general, a very low no. of factors helps with the narrative. However, even small changes/increase in the no. of factors can change the results

It is therefore very important to look at precisely *what* the factors are loading onto, and then judge whether this is in line with what the practitioner is really trying to do

### Great Moderation

Background:

Mainly interpreted and documented as a decrease in volatility in output and prices

Therefore, keep this in mind when running the test

The standard ON estimator selects something like 3, 5, 2 factors

This is usually sufficient to capture the main output and price variables, and the results from this are fairly robust

Empirically:

First Regime:

1. Output
2. ...
3. ...
4. ... Price

Second Regime:

1. Output
2. Price

The above looks quite strange, but it is fairly straightforward to show that this sort of "re-shuffling" has be represented as a Type 2a break

Therefore, for the purposes of disentanglement, minimal projection is actually necessary...

I think in retrospect this should be a main selling point of the paper, because it is not at all obvious that from a technical standpoint, out method can accurately accomodate for this

### Global Financial Crisis

First Regime:

1. Labour + Output
2. Price
3. Consumption

Second Regime:

1. Labour, Interest, Consumption
2. Consumption
3. Price

The above looks to be *at least* a Type 2a break

AHER suggests only 1 factor, i.e. only labour/output. If this is the main focus, then this is a Type 2 break only

ON suggests something similar to the above

BNIC suggests something like six factors, and this tends to include more effects of interest rates and stock prices. When these are included, there is too much noise, and the null can't be rejected at all

This suggests that the labour/output factor is a type 2 break, but the remaining two factors (Price and consumption) are perhaps at least Type 1 breaks. There is some rudimentary evidence for this, it does seem that not all series have changed in the same way.

