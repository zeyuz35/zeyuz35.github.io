---
id: kdWEzmfE1rSZAZX1GwXsP
title: Fama French
desc: ''
updated: 1637885521801
created: 1636426914350
---

Fama French Data.

Note that the goal in financial econometrics is to typically try to come up with factors which explain the *in sample* variation of returns.

Fama French factors etc, were *never* intended to be used in any shape or form to be used for *prediction* of stock returns (not that this has stopped people from trying).

Financial factors are really intended for investors to understand the different exposure effects in their portfolios.

## Data

The raw data is always available from Kenneth French's website. However, data is all offered in the form of excel files, which are notorious to work with.

https://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html

Instead, use the frenchdata package.

## 3 Factor Model

The most famous Fama French, the 3 factor model refers to the market factor (usual beta in finance), and the addition of Small Minus Big (SMB, size effect), and High Minus Low (HML, value effect) factor. 

The "factors" are the returns of a portfolio that longs Small stocks, and shorts Big stocks, where size is made according to a sort. The returns of this portfolio is then supposed to proxy for the underlying effect.

## Momentum Factor

A momentum factor of some sort if well documented to explain returns in sample by many sources. 

Momentum is basically technical analysis - i.e. returns have some sort of autoregressive structure to them in some form.

This is controversial, because efficient market hypothesis implies states that there should not exist a momentum factor in markets. 

This is why this tends to be treated as something separate from the Fama French data.

## 5 Factor Model

Fama and French more recently introduce a 5 factor model. This is less well known.

RMW is a profitability factor. 

CMA is conservative less aggresive.


