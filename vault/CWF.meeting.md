---
id: BYVYRGj8HV4cxZX1SLbeR
title: CWF Meeting
desc: ''
updated: 1639029551264
created: 1638767677915
---

## Checklist of what has been done

Basic literature review

## Model

Based on an arbitrary selection of candidate models, try to combine and weight their forecasts according to how correlated their forecast residuals are.

Bonsoo proposed the main model setup of how to write the model out and set up the optimization procedure

I proposed the mechanism for how to actually estimate the covariance matrix of forecast residuals. The steps to this are:

1. Set aside a training set
2. Fit a model to this training step
3. Calculate a h-step ahead forecast residual for the model
4. Repeat for all candidate models
5. Move the training set forward by 1 step (either recursively, or as a window) and repeat

The above procedure is then repeated, until a sufficiently large enough sample of h-step ahead forecast residuals is available. Standard HAC based methods can then be run on this to yield a consistent long run covariance matrix of forecast residuals.

The above was implemented as it intuitively made sense, and just to get a proof of concept done. 

The theoretical validity of the above needs to be established. Or, something else (such as block bootstrap).

Note that this seems to be the most computationally demanding part of the project.

## Code

Basic OOP implementation of the model.

This 

Note that this relies on some helper functions from my PhD:

- macroXTS class for dealing wit empirical data
- DFM methods for anything that is factor related

## Roadmap

Bonsoo mentioned that some theoretical properties would be nice to established, at least with the introduction of some stricter regularity conditions.

## Suggestions

Try to use different data, e.g. Unemployment (tends to be regarded as easier to forecast)

Also consider 2nd log diff of CPI, because sometimes people (such as McCracken) document this as being I(2).

Plot the series of covariance matrices, correlation matrices, etc over time

Investigate why using a correlation matrix instead gives more "equal" weighting

Investigate with simulation mixture models (this should give equal weighting)



## Small Simulation Study

## Small Empirical Study


