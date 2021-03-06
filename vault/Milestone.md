---
id: dd60rjxfs9snlsi3pj5luy0
title: Milestone
desc: ''
updated: 1648598013735
created: 1646968107029
---

# Jian Jie - Bayesian Mortality Modelling

Serif font

52 slides!

## Literature Review

## Paper 1

DFM, consider special case of DFM with only 1 factor

Generalize the DFM to include extra set of exogeneous regressors, such as health expenditure

Bayesian Inference. Everything is done bia the standard Gibbs Sampler. FFBS algorithm.

Findings

Why are the plots hand annotated? These are posterior plots.

Plots are not labelled, unclear what they are...

Counterfactual analysis: increased health expenditure increased life expectancy

None of this seems very novel, results are fairly in line with heuristics

There are way too many plots, and they all look very similar. Unclear what is supposed to be the highlight...

## Paper 2

Second paper extends the Lee Carter to a clustering and sparse framework

Figures not labelled properly, needed Latex fix

Drawbacks of DFMs

Over parameterization

Model Interpretability, lack of identification, hard to interpret latent factors

Regularization in Bayes:

- LASSO
- Ridge
- Minnesota Prior
- Spike and Slab Prior

Dimensional Reduction

- Principal Components
- Compression Regression

## Proposal

Sparse DYnamic Factor Model

Introduction of an indicator function, which is a multinomial distribution

Coherent Forecasting

Prove that SDFM is age coherent (log difference between two age groups is Op1)

Prior specification:

basic idea is to shrink the movement of the factors towards a co-integrated VAR process

## Challenges

Different samplign frequency

Publication delays

Stacked/mixed frequency VAR approach

nowcasting literature

## Contribution

Letting the data speak for itself, and not artificially splitting into groups of age bands





# Shirley Sun - Australian Electricity Generation Expansion Planning

Supervisors: Heather Anderson, Wei Wei, Xibin Zhang

This seems quite ambitious, but is mostly applied

The presentation overlal is quite good. A little too much of just reading from slides however

39 slides, but she goes through them quite quickly

Pressed for time

## Introduction

Energy is being transitioend to renewables, net zero to 2050 goal

Climate Change Issues, whichcould lead to extra uncertainty and requires new stochastic modelling

## Objectives

Analyse socioeconomic factors concerningg energy transition

Find optimal allocaton of six types of renewables

Find best timeline to replace traditional power grid

Find optimal retirement order for the eisting coal plants

Evaluate forecast

Difficulties:

- Dynamic optimzation path for energy transition
- Most literature only focuses on one certain aspect
- COnstruct theoretical model to quantify 
- Framework of indivduals, society and government

GEP

## Methodology

### Deterministic GEP Model

GEP model contains:

- Basic economic objective
- Set of decision variables
- set of constraints

Initial deterministic

- Min NPV

Main objective is to simply minimize NPV, after specifying the cost function

Minimization function was a little unclear, which parameters are to be optimized are not clear

### Climate Change Impacts

Just an overview of what can happen

### Empirical Application

Mostly description of dataset

Tables are not presented in the clearest way

Numbers not aligned, decimal places hard to read, etc

### Discussion




# Lu Wang Deep - Neural Networks on Nonparametric Regression with High-dimensional Data

Supervised by Jiti, Bin, and Yanrong Yang

28 Slides

She seems to be going through the slides very slowly

Seems like an empirical/applied paper for now...

Mervyn seems to like this presentation a lot (just the presentation anyway...)

## Motivation 

Suppose we have a set of high dimensional data

Existing tools: LASSO, Screening, random matrix theory, functional data, etc

Look at low rank representation (factor representation)

There exists an extension to the factor model by incorporating nonlinearities (boosting, Stock and Watson 2012)

Kernel methods (Li and Racine), Sieve methods (Chen 2007). However, when the no. of factors is too large, this will fail computationally

COnsider use of neural networks to overcome this issue

### Neural Networks

Standard neural networks background given

Cybenko 1989 provides that even a single layered feedforward networks are capable of approximating any continuous function 

Hornik 1989 and Hornik 1991 provide similar results

Typical assumptions:

Structural assumptions on the target function

Distributional assumptiosn on the input x

## Proposed model and estimation

Use PCA to obtain factor estimates

Then use DNNs with factors as inputs

She uses the "bar" normalisation instead of "tilde" - likely where Bin got confused

Minimize L2 loss of y - m(f)

## Simulation and Empirical Study

Standard DGP

Standard DNN, compared with OLS, PCR and KNN for non-parametric regression

Need to consider a spectrum of simulation designs

Figures not labelled properly

## Empirical Data

Uses the Gu et al dataset

How did she deal with missing data?

Preliminary results 

### Chapter 1

Aim to derive expected value of L2 loss

### Chapter 2

Extension to cluster

### Chapter 3

Extension to additive factor structure

Now the loadings are themselves are functions, and they wish to estimate them

How did she get the bibliography to span multiple pages?

## Discussion

Where exactly is the nonlinearity coming from?




# Ashley Andrews - DOes Information Leakage Compromise the Use of News as a Forward Looking Indicator for Short Term Volatility

Sueprvised by Klaus, Wei Wei and Bonsoo

63 Slides!

The slides are very sparse, only about 2 bullet points per slide

He is going at about 1 minute per slide

This was rough, only on slide 34/63, but 5 minutes left to go

Ran severely over time

Gael however is nice and gave the extra time

Appreciate the sparse slides, but sometimes relevant things are spread out too much

Sections/subsections would be nice

Mid Candidature Review

They get 35 minutes

Seems like a very ambitious applied paper

At times, it feels like there is a little too much detail

Lots of praise for the amount fo work put in, agree

## Terminology

Does volatility arrive more timely than news arrival?

Does this compromise FOMC announcements?

See if text derived measures can have any relationship with news impacts


## Data 

Ravenpack is a database for news input

Ravenpack already processes the news and sentiment for you

Convert sentiment to a factor variables, separated into groups

Volatility for interday is done via realized volatility

Intraday volatility uses realized kernel, which si robust to microstructure noise



## Model

Basically a FE model for the panel of data, y = realized volatility

Why 7 lags? Shouldn't this be 5 days? etc

Seems like a weak point, the data is organised around a 5 day week structure, but he's added in a 7 day lag 

## Results

Some fo the tables look slightly janky (esp with the colours)

Some fo the graphs are done via STATA

## Conclusion

He's only just finishing up the final write up of paper 1 and submitting

It looks like you need to submit he actual thesis 6 months before the end of the degree, to allow for feedback



# Ryan Thompson - Pre Submission

This is meant to be a full 45 minutes!

Apparently the report was very well written and summarized the papers very nicely

Report needs to report any changes to the papers, if any

Nice clean slides! Only 30 slides!

Pre submission seminars are allowed to be interrupted throughout the presentation

he talks like Filthy Robot and is very first person narrative

\pause without transparency, not something that I like personally
## Classical Inference

Hypotheses however usually are concerned about the centre of the distribution

However, the choice of which centre of the distribution is a little unclear

Usually mean, but could be median, mode...

Reproducvibility crisis in science

The choice of which centre to test can be cherry picked

## Familial Inference

Rather than test a single centre, test a family of plausible centres

Study and focus on the family induced by the Huber Loss Function, a mixture of MAE and MSE

It seems that this would be restricted to testing mixtures of the median/mean

## Method

bayesian nonparametric test

Pathwise optimisation routie

Exploits structure of Huber function

Implemented in R familial package, with familiar interface

## Data

Do mammal spend as much time sleeping as awake?

Bayesian procedure produces a posterior for the Huber family

## Testing Procedure

Target of inference is the Huber Family

Figures not labelled

Put prior directly on P

Drichlet Process (DP) a distribution on distributions

## Bayesian Bootstrap

Draw weights from dirichlet (1, ...)

Compute the minimization problem using the drawn weights

Highly scalable and trivially parallelisable

Using the bootstraps, compute the prob of null hypothesis

Count how many of the bootstrap samples was in the null hypothesis

Correspondingly, same for alternative hypothesis probability

Decision Rule:

Optimal decision minimises loss Lp

Matrix is setup such that it corresponds to the 0.95 level

## Optimization

Explort insight that mu(lambda) is piecewise linear in lambda

and thereforem the solution path is characterised by a series of n knots

Similar to lasso or something

This is actually genius!

Huber function is funadamentally realted to LASSO

These results are all really well explained, but I think it would have been better to organise these into lemmas, theorems, etc, though this is not Ryan's style for presentations

Note that LARS algorithm does apply to this problem, but turns out to be slower

## Monte Carlo

Figures not clearly labelled

Clearly explained (I think)

Similar results for other distributions, but Poisson one seems a bit strange...

## Empirical

Body Posture Study

Body Posture affects selective attention - do standing desks etc make a difference

Conduct a Stroop test (brain teaser) to 50 people with different postures

In their paper they conduct a bunch of individual test, all reject the null hypothesis

Multi task framing affects task performance

Transcibe the audiotrack of a video, but just the way the problem is presented

t test suggests rejecting the null

But the median, rank sum and new familial test are all not exactly robust to these choices!

## Discussion

Very good on timing!

# Ying Zhou - Parametric Index Models

Jiti Gao, Dr Kew

46 Slides, Pre submission milestone

Econometric Estimation for non linear models with stationary and non stationary regressors

## Chapter 3

This single index model only allowed non stationary regressors, adn cannot include lagged dependent variables

## Chapter 4

Modify the previous model to allow additional stationary variables, and lagged dependent variables

Slides are clean, but there is too much maths... Lots of substituting

Use the derivatives (Taylor approximation) to linearize, and use this as a staring value etc

This is quite rough to follow (eel tired), and I don't think there is an easier way to present this

Tables not labelled, and they all look too similar

Ying's work is mechanically sound, but not sold or well presented (motivated)

And is getting roasted by Mervyn's on style...

The writing apparently has improved dramatically a lot...








# Cheok - Bayesian Case Influence Analysis for Spatial Autoregressive Models

Catherine Forbes, Natalia Bailey

Looks like a lot of slides...

Wasting a lot of time on talking about the structure of the presentation...

Internet connection on his end is bad

5 minutes left, but only about halfway through

Slides are waay too sparse

## Introduction

Consider a dataset with some distinct clusters

Goal is to detect observations with detectable impact

## Model

Never formally defines SAR

p is a SAR parameter that controls degree of spatial dependence

W is a matrix of non stochastic spatial distances

Beta are some unknown regression coefficients

Can derive a full data likelihood from the expresson

Can introduce a set of priors 

## Bayesian case influence analysis

Introduces influence by deleting the kth observation

Recall that in AR1 case, we can still formulate the likelihood for kth observation removed

Introduce selection vector
## Illustration

## Future Work


# Ryan Zische - Sampling Variability on Forecast Combinations

Only 21 slides!

Forecast combinations are weighted combinations of forecasts

These are highly competitive (Makridakis, et al), dominated M4, M5

However, there is little attention paid to the impact of sampling variability

Optimally weighted two step combinations do not outperform equally weighted two step combinations
This is the forecast combination puzzle

Speculated to be because equal weights have no sampling variability

How does finite sample estimation error impact the performance of joint and distributional forecast combinations and the hypothesis tests thereof?

## Overview

Paper 1

One step is asymptotically superior to two step

All asymptotic sampling variability of two step performance comes from constituents

Paper 2

New insights into forecast combinations

One step beats two step in hypothesis tests of predictive accuracy

Tests of predictive accuracy have no size control and no local power for two step combinations

Paper 3

Parametric bootstrap and the distribution forecast combination puzzle

Two step combinations estimated using MLE

Sampling distribution estimated with parametric bootstrap

This presentation is focused on Paper 2

## Forecast combinations

Recipe

Obtain constituent models, parameterised by \gamma

Specify combination function, parameterised by \eta weights (Stone, Bates and Granger 1969)

Specify reward function S, or alternatively loss function L = -S (Hyndman and Koehler, Gneiting and Raftery)

Optimise \eta and \gamma wrt S, somehow

## One Step

Optimise \theta = \gamma and \eta, average reward S

## Two Step

\gamma maximises average reward S of model j

\eta then maximises the average reward, given \gamma (conditional on first step)

OR \eta is just a simple average

He should have defined notation first...

## Method

Measure forecast performance: expected out of sample reward S

Under regularity, one step estimator maximises the performance, but two step estimators do not

one step > optimal two step > equal weighted, asymptotically

One step is n consistent, but two steps are root n consistent, one step is super consistent

## Hypothesis Testing

Null:

No inferior predictive accuracy

Test statistics is similar in spirit to a Diebold Mariano test.

## Graphs

He spends way too much time on too many graphs on the same slide...

Important take away: outside of their theory, it is unclear what exactly happens

## Conclusion

Mervyn seemed to really like the presentation

But a common bit of feedback was that there were too many small ideas in one paper

Needed to brainstorm how to edit and sell the contribution for publication/referees

