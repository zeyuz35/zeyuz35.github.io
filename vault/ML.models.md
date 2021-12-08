---
id: kpyziz7LBSpI1Aqnx23nL
title: Machine Learning Models
desc: ''
updated: 1638413027059
created: 1637708903278
---

## Linear Models

The standard linear model. 

Note that these are also fit with quantile loss to yield the LADS estimator.

## Penalized Linear Models



## Random Forests

Note that randomforestSRC seems to be the most fully featured and optimized package for actually fitting random forests.

randomforestSRC is actually multithreaded properly, and supports MSE, quantile losses, survival losses, etc.

## Neural Networks

A disaster, and it seems that shallow learning (simpler models) tend to outperform deeper models.

Use tensorflow to fit these. A GPU is not strictly necessary, as the data and models are not actually complex enough. The bottleneck seems to be transferring the data from the CPU to the GPU, not the actual fitting. Still, it is marginally faster, so it is recommended to set this up properly.

See [[Software.tensorflow]] for details on setting this up.

## FFORMA Model Averaging

This was the second place winner of the M4 competition. 
https://github.com/pmontman/fforma

Note that the actual winner of the M4 competition used a smooth recurring neural network (ES RNN) method, by an Uber data scientist.
https://eng.uber.com/m4-forecasting-competition/)

## AWS DeepAR

AWS DeepAR is a state of art RNN based model, which is essentially a VAR (despite its name being AR), but instead of a strict VAR structure, regressors and the feature space are learned via an ML based approach.

The strength of DeepAR lies in

1. Being scalable, and easily deployable on AWS infrastructure
2. Being able to learn hidden features among a very large number of time series

The latter point is very important, as DeepAR was mostly formulated to forecast things such as consumer demand for products, and in this context DeepAR reportedly does well with an input of all possible catalogued sales data. DeepAR's own white paper even suggests that for simpler data structures with not as much data, simpler methods such as AR, ETS, etc perform much better.

Setting this up is not easy and expensive. See [[Software.AWS]] for details.