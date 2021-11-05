---
id: o5p95ZOzuszn4wAUYarUr
title: 8 Forecasting
desc: ''
updated: 1636096567801
created: 1635129375865
---

# Forecasting

This section deals with how factor models are used in the context of applied forecasting, and more specifically, how to forecast any $X_{it}$ series within the panel used to construct the factors themselves. I.e. this is not simply a factor augmented forecast exercise.

There are two main ways to make forecasts with dynamic factor models:

1. Direct forecasts, where data at $t + h$ is projected on the factors at time $t$
2. Recursive forecasts, wehre data at $t + h$ is computed using data at time $t + h - 1$ and so on

The first case it suffices to have an estimate of the factors, so usually PCA is used. 

The second requires the dynamics to be specified, so usually a state space approach is used instead.

## Missing Data

Unfortunately in applied work missing data is quite common, and there are in general two ways to deal with this in the factor literature.

### Omitted variables are uncorrelated with factors

This is the simpler, though unrealistic case. By definition, omitted variables are idiosyncratic in this case.

### Omitted variables are correlated with factors

The predictor is 

## PCA Regression Approach

## Genrealized and Dynamic PCA Regression Approach

## State Space Approach

## Mixed Frequencies (Nowcaasting/Backcasting)

