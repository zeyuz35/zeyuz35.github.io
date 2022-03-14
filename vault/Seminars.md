---
id: anyfw7yx1aac4eanbkxrerd
title: Seminars
desc: ''
updated: 1647007201156
created: 1646973001631
---

# Ambiguity with Machine Learning: An Application to Portfolio Choice

Not sure how many slides

This was a good pace, but he also got almost one whole hour...

san serif font!

Seems to be another applied paper, whose main contribution is a new uncertainty measure

## Intro

Risk vs Uncertainty

Risk is when a probability assignment can be done. Uncertainty is when probability cannot be assigned.

Investor is using ML as a guidance for portfolio allocation (mean var opt), but they are worrieed about model uncertainty

Focus on two key ingredient for such preference

ML models for expected returns

Characterization of model uncertainty via bootstrap principles

## Model

Focus on regularized linear regression models (LASSO)

Bootsrtpa method (weighted Bayesian bootstrap) to obtain a distribution for expected erturn across assets and across models

Reformulate markowits portforlio optimization problem in a risk adhjusted setting

Applies to any combination of assets considered in the portfolio exercise

Multi-asset case, we produce a matrix based uncertainty measure

## Assumptions

N x 1 vector of excess returns for N assets for each t

Returns are all conditionall Gaussian, a standard assumption in Markowitz and ambiguity literature

Assume that the differences in models are focused on 

True model is embedded inside this class of Gaussian Models

Conditional variacne matrix is not a sourcec of uncertainty

Due to reliance on LASSO, an implicit assumption of sparsity is made

## Robust Markowitz Problem

robust mean-variance preferenecs can be formulated as:

Lambda matrix

In absence of constraints, the solution to the above optimization problem is

Main focus is on the mu and Lambda matrix

## Sigma

View sigma as a data driven object, and view realized volatility as a predictor to it

Comptue an estimate of sigma using past daily data

## Proposition

A model uncertainty measure can be formulated by taking out the model risk (model sigma)

Translate original problem into something similar to a GLS problem

Weighted Bayesian Bootstrap

Empirical Uncertainty Measure

## Data

P index, treasury bonds,gold, cash

Fama French potfolios

Predictors

real time vintages from ALFRED Database

Fama French factors

Welch Goyal

VIX

Text data, Nick Bloom data library

Industry level based on Green et al, and WRDS, interactions between individual and macro

## Model

Uncertainty measures that exist include EPU (Bloom's), JLN, and arguably VIX

Model complexity seems to decrease over time, esp after GFC (seems to corroborate with DFM finding..)

Markowitz portfolio optimizaton wth uncertainy adjust portfolio outperforms benchmark portfolios

Perhaps is something that could be worth looking into?

## Expanding vs Rolling

Model complexity decreasing seems to be pervasive on expanding windows

This doesn't seem to be the case for rolling windows

Early fluctuations may be just due to small sample problems

Rolling windows tend to exacerbate small sample issues






