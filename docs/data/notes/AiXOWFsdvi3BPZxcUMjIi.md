
#hashtag 

A section dedicated to any Bayesian approaches found in the literature.

DFM estimation via Bayes methods exist, however, it is unknown if they offer any advantages over traditional PCA based approaches.

The main draw of Bayesian approaches seems to be the access to the Bayesian framework, which can allow for more complicated inference.

For example, if one were interested in modelling time varying factor loadings, then they could specify a law of motion for the loadings, factors and error term, and derive any relevant marginal posteriors directly via the Bayesian framework. This is the approach of del Negro and Otrok.

## del Negro and Otrok

The main paper which does DFMs with time varying parameters, and is the basis algorithm for many otehr subsequent papers to come. They allow for stochastic volatility in the innovations to the factors and the idiosyncratic disturbances. This means that the resulting DFM has a nonlinear state evolution in this dynamics, and so can no longer be estimated via traditional means such as a Kalman Filter. Their main contribution is the development of numerical Bayes methods to estimate such a model.

It seems that all other subsequent papers used this algorithm/approach, or variants of it.

## Mumtaz and Surico

An application of a time varying DFM estimated via Bayes in order to to study inflation persistence and predictiability across industrialized economies.

Their model introduces drifting coefficients (loadings) as well as time stochastic volatility in the factor. dynamics. The dataset they focus on consists of 164 inflation indicators (macroeconomic series essentially) from the G7, Australia, New Zealand and Spain (will need to check out this dataset later).

### Model 

Specifically, they model each inflation series for each country as a function of a country specific factor, and a common world factor. The factors (structural shocks) themselves are allowed to evolve according to an AR process, where the AR coefficients themselves are allowed to evolve over time. The idiosyncratic error is allowed to be a stochastic volatility process (i.e. error term itself is an AR model).

Due to a identification issue with the loadings, they simply force the first $k \times k$ block of factor loadings to be an identity matrix.

### Estimation

Apparently they have their code, data etc available in the online appendix, will need to followup.

## Brjornland and Thorsrud (2015a)

These authors focus on investigating whether the adoption of a fiscal rule is able to insulate a domestic economy from commodity price fluctuations. That is, do government spending limitations help with smoothing out fluctuations caused by commodity prices. Specifically, they focus on Norway, whose GDP growth and public sector spending is highly correlated with oil prices, and whether this is effective at actually stabilizing the Norwegian economy.

They do this via an application of a time varying DFM. 

Note that the authors make special note that as an alternative to something more complicated, one could approach this task empirically by splitting the sample along when the fiscal rule was implemented. This is consistent with external identification of a regime change/structural break. However, the drawback with this is that it is too simple, specifically the parameters within each regime are still assumed to be constant.

## Stock and Watson (2015)

An application of something similar to del Negro and Otrok's work. 


