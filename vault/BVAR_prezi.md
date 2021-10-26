---
id: 8QKn1l2AfuAU6zvm2C1qf
title: BVAR_prezi
desc: ''
updated: 1635212174688
created: 1635212169623
---
# Large Bayesian VAR presentation

Two main approaches to large datasets in Macroeconomcis

Gary Koop

DFM
Efficient, not prone to overfitting
Model specification somewhat involved (no. of factors, identification)
What if the data does no co move? (or only a subset co moves?)

VAR
Highly flexible, close connection to DFM
SUitable priors leads to computational efficiency
CUrse of dimensionality

Empirical work tends to find that large VARs forecast better somehow

Bayesian Prior 
Conjugate priors are very easy to work with
Other more fancier priors (e.g. LASSO, etc) are more algorithmically based (ML like)
However, these require MCMC which can be computationally demanding

How to decide between the methods?
Do a pseudo out of sample exercise, whichever one does better is better
However, this is time consuming, and can be sensitive to period chosen
IC or Marginal Likelihoods
However, these are hard to calculate, or sensitive to priors chosen (for likelihoods)
Numerical issues in large dimesnions
Implicitly reward one step ahead predictive capabilities of th Model

Summary of Paper
Develop an alternative method for choosing between factor models and large VARs
But why is there a need to choos ebetween? WHy not combine them together?
Use a new Bayesian VAR prior centred over restrictions implied by DFM (alternative interpretation)
E.g. Minnestoa prior is centered over values of parameters that people thought were sensible

Inspriation from SHIN Bhattacharya, Johnson
The idea behind this was to shrink possibly non robust non parametric methods towards a linear model

We use Gaussian (conjugate) priors as theoretical derivations exact

## Summary
Conventional Bayesian priors shrink estimates of a parameter towards its prior mean
Subspsace shrinkage priors are priors on function spaces
Shrink towards a class of functions
E.g. Bayesian non parametric model can shrink towards linearity
Here, we propose a new subspace shrinkage prior for the VAR which shrinks towards a factor model
This prior is conjugate and easy to implement
Scales very well to high dimensions

Ben made a good note about this, VAR is empirically better, however, this is shrinking towards a DFM, and this does not make intuitive sense
Loosely speaking, this new method is a Bayesian weighting scheme between DFM and large VAR
Empirically, they find about 20% DFM, 80% VAR

VAR tends to work better for US based datasets

Overview
Develop two version of this shrinkage prior
Non informative VAR prior + subspace shrinkage prior
Minnesota VAR prior + subspace shrinkage prior

Parameter w controls the degree of shrinkage towards the factor model

Estimate of w produces best combination of VAR DFM or can be used to select one or the other

Number of factors can also be estimated (co author is more exicted by this)

Allows dor selecting the number of factors and the weight associated with the DFM within a unified framework

Model properties illustrated using artificial data and a macroeconomic forecasting exercise
Seems to work well for simulated data
Seems to work slightly better for empirical data

See hjandwritten notes for model notation

Next step, combine this with traditional Minnesota Prior

This proves another result
Can be proven to 

Final
Need to choose
number of factors q
weight attached to VAR relative w
shrinkage (v)

A conjugate prior makes this trivially easy

Just use Monte Carlo integration over the three parameters (this is still reasonable)

Forecasting Exercise
FRED QD, 1960 - 2020
FRED transfomrations
Forecast GDP growth, inflation and Fed Funds Rates
forecast evaluation from 1990 to 2020
one quarter and one year ahead
RMSFEs and log predictive likelihoods
COnsider 12, 22, 78, 166 variable VARS
FOur subspace VAR approaches
Also include conventional Minnesota prior VAR and FAVAR
All VARs have lag length 2

Check actual paper for all results

No consistent results, however
Minnesota prior VAR forecasts better
But there are some cases where factor model forecasts better
Perhaps combination could lead to something better?

subVAR approach which combined Minnestoa prior and DFM
Most of the time this forecasts best
Choice of prior on w makes little difference

What about subVAR approach which combined flat prior VAR and DFM
small and medium VARs forecast well
However, subspace shrinkage (unless extremely strong) not enough in large and extra large VARs

SOmetimes, there are large changes in parameters in crises
E.g. VAR w weights switches from 0.1 to 0.8 in financial crisis thens witches back after end of crisis
I.e. time varying w
Authors note that w is never fully 0 or 1
However, a prior on w with specific mass on 0 or 1 could try to get around this issue

Extensions
Lots of other Bayesian VARs priors are being used
Stochastic Volatility extension?
- yes, this is possible, but no analytic results
- Decompose error covariance matrix into A0^-1 D A0^-T
This allows us eto work with one variable at atime, which is massively quicker with MCMC
COnujugate version of Minnesota prior has one shrinkage parameter v
Might want several: own lag shrinkage different from other lags, different equations having different shrinkage
Straightforward to develop MCM algo
These are all interesting extensions and feasible, as long as dimensionality isn't too large
Chan 2020 considers Bayesian VARs with erro covariance sigma kron sigma
Different sigma choices lead to SV, MA, fat tails, etc




