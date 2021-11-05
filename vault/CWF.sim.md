---
id: FPGOIfZj4F6lT1ANrKWdX
title: CWF Simulation Study
desc: ''
updated: 1636095383581
created: 1636095154775
---

Simulation study for covariance weighted forecasting.

## Motivation

The purpose of this simulation study is to implement very simple forecasting methods on a simple dgp for which we know which ones would perform well, and see how the method works.

Thus, it acts as a bit of sanity check.

This is currently just ordered as a bit of a journal (chronologically).

## Experiment 1

The data is simulated from an AR model, and the constituent models are fixed $rho$ AR models.

The method did not work with this setup, because the residuals from all constituent models behaved very similarly. 

Hence, this leads to a development of a regularity condition that the residuals of all constituent models cannot be too collinear, as then the covariance matrix will be close to singular and difficult to invert.

## Experiment 2



