---
id: 6jScjSKL9hxSIPTbWMgAH
title: Inflation Forecasting Review
desc: ''
updated: 1636339491300
created: 1636095787485
---

Inflation forecasting review section.

Inflation forecasting is a prominent topic within the empirical forecasting literature. The results here are mainly a summary from Faust and Wright 2012 "Forecasting Inflation".

Note that was state of the art as of 2012, and so by now is perhaps a little outdated. The authors note that as of the time of writing there was an explosion in the inflation forecasting literature. 

Also note that "vintage" datasets were considered to be quite difficult and new-fangled back then...

## Real World Motivation

In general, Central Banks aim to keep inflation stable, maintain an efficient level of employment, and contribute towards the economic prosperity and welfare of its citizens, via the use of monetary policy (this is what the Reserve Bank of Australia states, and is essence what most other central banks' mission statements are). With this in mind, the New Keynesian approach to monetary policy explicitly requires the use of optimal forecasts, is most effective when it is well understood by the public.

It is for this reason that lead to central banks announcing forecasts of inflation and other key variables to the public, and is called "inflation targeting". 

A key note of this review is that subjective based models of inflation forecasting seem to still outperform actual model based forecasting. This is noted to be in stark contrast to GDP forecasting, where even very simple time series models do better than most subjective forecasts.

Another key note is the inflation forecasting done by the central bank and inflation forecasting done by the general public are completely different ball games. The cental bank has control over monetary policy, which in turn affects inflation, so the central banks' forecasts depend on what they anticipate their future monetary policy decisions to be. This leaves central banks two options: integrate/average out over all possible policy decisions to yield an unconditional forecast, or produce *conditional* forecasts. The Fed's Greenbook and Bank of England's forecasts are both conditional forecasts. 

## Data and stylized facts

It is noted that inflation forecast evaluation is regarded as impossible before about 1980, simply due to data availability issues. 

US inflation is well known to be much more quiescent (dormant) and harder to forecast during the Great Moderation (1985 - 2007, though the exact timing is controversial)

It is noted that most macroeconomic models are generally viewed as a sort of "first order approximation" around a local steady state. The implication of this is that it may ne unreasonable to expect any model to perform well in all scenarios. This is empirically what is seen on most macroeconomic models - the state of the art models are always reported to perform very well on the sample period the authors focus on, but when extrapolated, do not work very well.

It is therefore suggested that it is more "reasonable" to focus on models that perform well in "normal" times, though again, this is hard to define.

### Measure of Inflation

Inflation is well defined as an economic concept, but rather poorly defined in a concrete way. 

Four price indices are considered:

- GDP Deflator
- Personal COnsumption Expenditures (PCE) Deflator
- Consumer Price Index (CPI)
- Core CPI (CPI excluding food and energy)

Though some of the series above are now available at the monthly series, the focus is on using quarterly data. Note that the choice of which specific price index doesn't tend to matter too much, as they tend to move together, though their long run behaviour may differ somewhat.

For example, CPI tends to be about 0.3% higher than PCE, because regular CPI does not use chain-weighting, and so has a well known upward substitution bias.

The inflation rates are computed in an annualized way:

$$
\pi_t = 400 log(p_t / p_{t - 1})
$$

where $p_t$ is the price index at time $t$. 

Forecast errors are computed as actual - forecast value. Note that this is sometimes very difficult - the definition of different price indices can change over time. However, this is futile, and most sources, including the Greenbook, do not do anything special regarding this.

Error metrics used are out of sample only, because in-sample metrics are dumb.

Root Mean Square Percentage Error is reported. In addition, its relation to a benchmark is also reported, such that a ratio of < 1 means that the model is doing better than the benchmark. 

The paper also does some hypothesis tests on the forecasts, such as Diebold Mariano tests, but these are controversial. 

## Forecasting Methodology

Quarterly inflation rates for the *middle* month of each quarter are made. The first set of forecasts is made in Feb 1985, and the last in Nov 2011. 

Forecasts are made for the current quarter ($h = 0$), corresponding to a nowcast, to the next 8 quarters ($h = 8$). 

## Forecasting Methods

1. Direct Forecast, on lags

2. Recursive Autoregression (RAR)

3. Phillips Curve motivated forecast

4. Random Walk Model

5. Unosberved Component Stochastic Volatility Model

There does exist some Stock and Watson code for this, but this requires Bayes/MCMC and is too hard to implement fully.

6. Autoregressive in Gap Form

7. Fixed $rho$ forecast

8. Phillips Curve in Gap Form

9. Phillips Curve in Gap Form, with time varying NAIRU

10. Term Structure VAR based forecast

11. Time Varying Parameter VAR (TVP VAR)

12. Equal Weighted Averaging (EWA).
This is a special case of covariance weighted forecasting, where the covariance matrix is simply ignored. This needs to be implemented as a sort of "control".

13. Bayesian Model Averaging (BMA)

Assigns a prior over the parameters of the $n$ models used in EWA, and a flat prior that each model is equally likely to be true. 

This is quite complicated to set up, however, it would be nice if there exists some theoretical link between CWF and BMA.

14. Factor Augmented VAR (FAVAR)


15. Dynamic Stochastic General Equilibrium Model

Complicated theoretical model. Best not to spend too much time reading into this and getting side tracked.

16. DSGE with shifting local mean.

Similarly, ignore due to complexity.

17. Subjective Forecasts
- Blue Chip Survey
- Survery of Professional Forecasters
- Federal Reserve Greenbook

In most propose models, $rho$ is chosen via the BIC, and this no. of lags is kept constant across *all* models which use $rho$ as a parameter. Note that there is some evidence that BIC does best for direct forecasts, whereas AIC does best for iterated forecasts.

Some methods which are not included in this list include:

- Threshold Models
- LASSO and other selection models
- Bootstrap aggregation models
- Household survery expectations
- Extraction of inflation forecast from inflation related financial instruments

## Results

The benchmark model chosen is a fixed $rho$ AR model, because this is very simple.

### Subjective Forecasts do best

Good forecasts must account for a slowly varying local mean. It is particularly noted that any models that assume stationarity do particularly bad.

### Nowcast Comments
Often, there is special external information available at horizon zero, which can make subjective forecasts much better, and this is what is observed. An example given is how the Bank of Canada anticipated an enormous hike in lodging prices for the 2010 Canada Olympics, and took this information into account when constructing the relevant nowcast.
Good forecasts begin with good nowcasts.

### Heavy shrinkage in information improves inflation forecasts

## Financial Crisis

Surprisingly, the crisis period does not affect the relative performances of different models.

## Phillips Curve

The Phillips curve motivated models all did very poorly.

## Other Notes
