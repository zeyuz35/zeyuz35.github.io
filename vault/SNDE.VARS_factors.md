---
id: vv5su472k0ac84j4m0v6qn8
title: VARS_factors
desc: ''
updated: 1647015523162
created: 1647007221507
---

# Forecasting Sovereign Defaults

Graphs done in excel

Large increase in govvernment debt/gdp

Moodys described 2020 as a record year for sovern defaults

what are the quantittaive effects of covid on sovereign default probabilities?

Panel VAR where intercepts are country specific

unerlined latent risk of the vent is a VAR endogeneous variable, and it is directly linekd to the binary variable representing the event history

There are predictive methods that exist at trying to predict sovereign default probs

However, usually these did not work with panel data

## Previous literature

Global factors have a critical role in diriving fluctuations of CDS spreads

But, CDS spreads are only available for advanced and emerging economics

## Method

Default Probabilities are estimated at quarterly frequency using sovern default spreads

Global variables: global IP, commodity (Killian), US treasury bill rate, excess US bond premium to measure global business cycles

DOmestic variables: yoy GDP growth, government debt, debt ratios

Measurement of DYnamic Effects

- Global and Domestic variables to the prob of default

COmputation of conditional forecasts

## Model Setup

Sct is binary indicator variable for default

Sct is linked to latent zct (measure of risk)

Wt is a w x 1 vector of global variables, w = 3

Xct is m x 1 vector of domestic variables for each country, m = 4

Yt = Wt Xct zct, chuck Yt into a VAR

Impose restrictin that innovations are unit variance for identification

Estimate via Gibbs Sampling

Assume common prior for each intercept

These estimation strategies all look very straightforward...

## Results

Why are these presented in excel? Figures not labelled properly

## Forecasting

Compute country specific forecasts for each global variable

Average these

Then based on these, then compute forecasts

Use logscore for each country, and averaged across M countries

Diagonal of elementary score, when binary events are rare but have high impact consqueunces (DES

Out of sample, compare with dynamic probit model (microeconometrics)

Consider differences between scenario based and baseline predictive probabilties for 2021 and 2022

Awful plots...

They do a sort of counterfactual, forecast with and without 2020 covid data

Also, McCracken looks really old IRL

Struggles with time and finishing on time

## Conclusion and other notes 

Default probabilties depend on both domestic and global factors

Author has not run robustness checks just yet

# Reordering variables in VARs with stochastic voltaility

Strange windows software, I think he intends to annotate...

Strange, scrolling through slides

Ugh, preview of results

Spends too much on the outline of the actual presentation

## Motivation

stochvol VARs are commonly used in forecasting and structural exercises

Popular specification models the covariance matrix of reduced form

Matrix reduction is just meant to facilitate dimension, not to embed structural restrictions

Pro: using Bayes, estiamtion is standard

Con: Posterior distrbiutions parameters is not invariant to ordering of variables...

Contribution:

- Document efect of different ordering son both forecasting and IRFs
- Provide supporting an alternative, ordering invariant stochastic voltailtiy specification

BVAR wiyh standard SV specification, ordering matters for both point and denstiy forecasts

BVAR with alternative SV specification delivers compteitive forecasts, and it is immune tovariable ordering problem

Alternative estimation seems to delvier plausible IRFs

## Ordering Probkem

Slides are a little dense.

Distributions depend on variable ordering!

### Other Approaches

Estimate BVAR using many/all orderings, compare/combine results somehow

This is computationally infeasible

Alternative specifications of stochastic voaltility

- Inverst Wishart specification
- Ordering matters for density, but not point forecasting ? (contradiction)
- invariant SV specification

## Model

SV via inverse Wishart does not require trianguylar decomposition

but ARIW cannot be cast in linear and Gaussian state space, so a particle Gibbs with ancestor smapling is required

## Data

FREDQD

Rough, should ahve ended, but only on slide 8

## Results

No clear pattern for VAR ordering

No theoretical results, this is an applied paper

The ARIW seems to be better for forecasting

# Dynamic Mixture Vector Autoregressions with score driven weights

Regime swtiching models

Proposea  model that allows for time varying mixture weights

Estimation and Inference is feasible via the likelihood

This mixture model can be viewed as a generalization of other existing models such as Markov switchig, static mixture, etc

Can write down likelihood, gradient, etc and formulate a score driven MLE optimization

This is a nice formulation, hopefully there is an easy to easy implementation

Why do the porbabilities for markox seem to have an asymptote at 0.2, 0.8?

# On the real time predictive content of financial conditions for growth

He sounds gay

## Motivation

Surge in quantile forecasting, and a lot of people are excited about GDP forecasting

Bulk of litearture uses a current vintage

However, NFCI requires the use of real time revisions

Create real time unofficial vintages of the NFCI

Diebold Mariano may not apply, becuase models are all nested, predictors and predictand are subject to data revisions

Use results of Clark and McCracken to get around this issue

## Comparison of vintages

Some of the tables and plots are not very good, but forgivable given the large vintages

Also, I think McCracken is enough of a big shot that it doesnt matter

## Derivation of Tests of Predictive Ability

Model data revisions are regular and finite

Combination of a few different results, and can show that the predictive loss can be asymptotically normal, with a way to derive asymptotic variance

## Conclusion

Seems that real time vintages are better, leading into recessions

Intuition: current vintages may be over smoothed around turning points

This may be interesting as a data source for things focused on turning point analysis




