
A document summarizing state space approaches to estimating DFMs. 

These are first approaches taken by the literature (and is likely the approach most people would think of initially) to estimate DFMs. 

Unfortunately, such estimation requires the explicit specification of state space equations, which often require strict and unrealistic assumptions such as Gaussian errors in order to be estimable, such as via a Kalman Filter.

Additionally, these methods suffer from the curse of dimensionality, and as such they have fallen out of favour.

However, note that a natural extension to these is done via a Bayesian framework, which looks promising and very flexible. See [[Bayesian]].

## Numerical Computation

See [[Kalman_Filter]] for details.

## EM Algorithm

[@barigozzi_quasi_2020] provides a strong theoretical results for the EM estimator, as viewed as a QML estimator.

See [[State_Space.inference]] for more details.