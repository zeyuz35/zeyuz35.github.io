
A summary for estimators of $r$, the number of static factors.

## Bai and Ng

The most famous and widely used estimator. For practical purposes, they introduce 3 different IC, which are asymptotoically identical. However, in finite sample, IC1 > IC2 > IC3, and IC2 is the most used one in practice. 

Note that these are only reasonably behaved for a data sample that is large enough, relative the maximum no. of factors. If rmax is too large, the IC will diverge, and simply estimate as many factors as you allow it to. 

## Onatski (2009) ON09

Onatski derives hypothesis tests regarding the number of static and/or dynamic factors in a DFM context, related to the empirical distribution of eigenvalues.

Note that this is a specific hypothesis test, so it difficult to use in a practical sense. I.e. why set up the null hypothesis to test for a specific number of factors?

MATLAB code is available from his website. However, this isn't too useful (for now), so conversion to R is on hold.

## Onatski (2010) ON10

Related follow up, Onatski produces an actual method to determine the number of static factors.

Onatski states that this outperforms Bai and Ng in two key ways:

- When the signal to noise ratio is low, Bai and Ng tend to underestimate the number of factors
- When the degree of autocorrelation in the idiosyncratic error tends to be high, Bai and Ng conversely overestimate the number of factors

Empirically on non-synthetic data, Onatski's method tends to estimate less factors than Bai and Ng, so presumably this means that the autocorrelation is high. As usual, it is unclear what is going on on real data.

They do especially note however, that their estimator tends to underestimate when some of the static factors are very weak. This is plausible, if some of the lags of the factors (true dynamic factors) have very weak correlation coefficients. 

Estimate r as the largest value of $k$ for which the different between the $k$ and $k + 1$ eigenvalues of the covariance matrix exceeds a threshold. This overall corresponds to finding the "largest cliff" in a scree plot.

Implementation converted to R from Onatski's MATLAB code.

Note that this is essentially runs sequential tests for the number of factors in a DFM, and therefore only results in an estimate. There is no corresponding plot function for this, accordingly.

## ABC 2010

The estimator of [@alessi_improved_2010], which is a modification to the [@bai_determining_2002]'s IC for improved penalization. 

However, this method requires the sepcification and tuning of two extra hyperparameters, and how to do this is unclear.

There is MATLAB code for this, and conversion is put on hold.

## Ahn and Horenstein 2013 (AHER, AHGR)

Ahn and Horenstein derive an alternative estimator for r based on the behaviour of how the eigenvalues change/grow. 

This is corresponds to finding the largest "relative cliff" in a scree plot.

There is the standard "eigenvalue ratio" and "growth ratio". 

## Notes

On simulated data, these all perform quite well. However, empirically, it has been observed that they perform very differently.

In particular, it has been noted that:

- 
- 
- 

This can partially explained by the following conjectures:

- the degree of auto correlation is the idiosyncratic errors terms is high
- asd
- asd

