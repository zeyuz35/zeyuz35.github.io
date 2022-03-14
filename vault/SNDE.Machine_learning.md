---
id: TwPN46hu5UXQmmOBlLBr3
title: Machine_learning
desc: ''
updated: 1646930392170
created: 1646923610551
---

# A4 Machine Learning Stream

...may drop between other streams in they are more interesting

# Forecasting with Var Text and DFM text models

Can central bank communication improve the forecast of standard macro variables?

sand serif font!

Federal Reserve is mostly 98 percent talk, 2 percent action

Thorsud used tone adjusted topic built based on a Norwegian newspaper in a DFM to nowcast

Topics/first stage measures are estimates left for future research

## Idea

Factor augmented models, factor models gelp explot additional data sources without being identified as specific economic concepts

Latent Drichlet Allocation is a Bayesian factor model for discrete data, with factors represting topics

text variables are textual factors

LDA is considered to be the de facto standard for text mining and doing sentiment analysis

Results is a bunch of textual factors Xt

## VAR model

Just add Xt textual factors as exogeneous regressors

Results presented awfully, learn how to bold/asterisk significant results!

## DFM

VAR in factors essentially

Benchmark: FREDMD

Estimation is via Bayesian, but using Bai and Ng criteria to select no. of factors

FOMC textual factors seem to improve forecasts

## Thoughts

This seems like a very straightforward applied paper. OK nvm, bulk of the work was in cleaning the test data

# In search of non-linear dynamcis in the Arctic with Deep Neural VARs

Serif font used

CAR do the Arctic

Plain Bayesian Autoregression

Compromose between fully structural and purely statistical balck box approach

Models a dynmaic system diverging towarsd a physical constiant of 0 SIE

Asses the importance of different variables in amplifying various forcings (feedback loops)

## Data

8 Different Arctic variables, e.g. temperature, sea ice extent, total cloud cover, etc

Take out seasonality

12 lags, Minnestoa Prior, Hyperparamters tuned according to Giannone 2015

Robust to different orderings

Air temperature shcoks are very transitory, but CO2 shock has a much more permanent shock on sea ice extent

Not too surprising...

## Going Deep

Previous Bayesian Var was linear... 

Throwing everything into a neural network is not optimal. Neural networks and random forests may not pick up on auto regressive structure.

Less necessary regularity possiblities, and the model is hard to interpret

Macro RF does not allow for extrapolating betat, which are important

A generalized TVP problem can be solved by casting a specific form of Deep Neural Networks

Gneerate time varying parameters via DNN, then chuck these into a traditional linear specification to get the final fitted values

Currently, everything is a WIP, only structure is provided

# Nowcasting Norwegian Household Consumption with Debit Transaction Data

## Motivation

Macro aggregates are typically only available with a lag, leads to need for nowcasting

COVID represented needs for reliable high frequency indicators that can track economy

Debit card transaction data is promising candidate indicator for demand side

## Contributions

Evaluate point and dentisty forecast accuracy of debit card data for quaterly consumption

MIDAS to handle mis match frequency

Document superior performance, more than 50 percent sometimes. 

Economic and statistically significant

Striking performance of the debit card data during the pandemic

## Data

Norway is a near cashless society

Covers all data from BankAxept, which is a comprehensive database across all banks

## Models

Benchmark: AR model

ARDL MIDAS Models

Goofle Trends indicator was constructed via PCA

## Thoughts

Started off strong, but presentation of results was quite poor

# Time interval choices in forecasting direction of stock prices changes using technical indicators

Powerpoint with calibri!

Very poor presentation, too much info at once

Technical indicators are often used as inputs for ML algorithms to forecast stock price movements

Selection of different time intervals is also an important choice

Forecasting horizon, teim intervals for computing features (input windows), and intervals used for tuning

Not much research on the effects of mentioned time related settings

Highest performance for SP500 is suggested for equal inoput length to horizon (no source given)

Does the same conlusion hold for CEE and SEE countries?

## Main Objective

Ibestigate how varying the foreecast horizona nd the input window length for calculating technical indicators affects the predictive performance on forecasting the direction of change of chosen CEE

Classification Problem

Stock price increased, or stock price decreased, as opposed to standard predictive rgression for continuous variable

Calculate 18 technical indicators
Tested combinations of time intervals for different technical indicators

## Data

CEE and SEE Indices

60% taken for first training set

Rolling forecasting origin is used (time slices)

Srprisingly she opted for R for this exercise

Accuracy used metric

Results not presented well, figures/tables not labelled

