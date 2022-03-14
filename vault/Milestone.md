---
id: dd60rjxfs9snlsi3pj5luy0
title: Milestone
desc: ''
updated: 1647221711852
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



