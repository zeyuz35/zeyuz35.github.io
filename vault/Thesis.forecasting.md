---
id: fyy0dueuurjyz1rerk1y8zu
title: Forecasting in DFMs subject to instability
desc: ''
updated: 1649125800269
created: 1649125800269
---

## Overview

This is really an updated study of Stock and Watson 2009, with a more specific emphasis on how
different types of breaks could affect forecasting

This area of research is very barren! Surprisingly...

These papers were mostly formulated before the advent of break classification

Therefore, assuming that the disentanglement chapter works out (and it seems to be), go ahead
with the assumption that breaks can be tested and estimated for, and the type of break can be
discerned

Refer to SW2009 for a very comprehensive overview

Related: Corradi and Swanson

Initial thoughts: 
Just try to replicate this (original code is in GAUSS, disgusting!)

## Model Setup

SW use the setup that is very in line with the applied literature (as opposed to Bai and Ng)

It is clear that the forecasting regression for Xit is

beta (lambda Phi) Ft + a(L) eit

Beta therefore is subject to instability from both the loadings and factor dynamics (Phi)

1. Lambda - time varying loadings (Type 1)
2. Phi - factor dynamics (Type 2)
3. Idiosyncratic shocks (can't be helped, ignore)

However, estimation via PCA is already consistent for Type 2 breaks
If you use PCA to estimate F, then you already have Phi(F)

Conjecture: Type 2 breaks are safe to ignore

Type 1 breaks require augmentation




