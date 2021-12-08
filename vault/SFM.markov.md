---
id: XiJC0xxXNzTGVmJGnTgDE
title: Markov Regime Switching
updated: 1638412893730
created: 1635422015099
bibliography: [references.bib]
reference-section-title: References
---

#markov #regime

Luke Hartigan's thesis also contains an approach to markov switching for factor models, however, haven't spent the time needed to read into it too much yet.

[@liu_regime-switching_2017]

Does not seem to be a very well known paper, despite arguably being technically sound.

An extension of static factor models which allows for factor loadings to switch according to an unobserved markov process.

Unfortunately estimating this is quite difficult, and the resulting estimates don't make too much sense.

## Notes

This method only works reasonably well for 2 regimes, 3 regimes and above it requires a LOT of data for convergence.

The regimes are not labelled, so it is difficult to analyse how well the simulation actually is (not sure how they got around this).

And most worryingly, the estimated regimes switches occur much too quickly, to the point where a rug plot is needed to visualize the rapid switches. 

For their empirical study, they focused on financial data, for which this mya be arguably reasonable, but this is not the case at all for Macroeconomic data.

For what it's worth, the frequency of switching increases a lot around crisis times/changes in volatility, so perhaps this is just another way of picking heteroskedasticity? Possible extension here.

## Implementation Details

Holy hell this was complicated to get working, even with their spaghetti code.

This will return estimates of the regimes across time, and it tends to switch back and forwards a lot.

These will need to be plotted with something like geom_rug().

### Dynamic Factor Model with Markov Switching

There seems to actually be a very large literature on MS DFM. However, these are very old and all of them make the limited assumption that the data only has ONE common component (ONE factor).

The paper by Liu and Chen is the first seminal paper (that I know of) is the first and ONLY paper that actually extends DFM to markov switching regimes.

#### Liu and Chen (Statistica Sinica Paper)

Give a panel of multivariate time series, and k regimes (typically 2 for convergence reasons), this paper proposes a DFM with factor switching according to a markov process.

The underlying markov process is assumed to be latent (unobserved). Note that the algorithm can also work with an observed state variable if needed.

I.e. DFM as usual, but the factor (spaces due to identification issues) switch in either regime.

Algorithm: given a T x N panel, and k = 2 regimes, estimate:
- d = no. of factors in each regime
- tran_est = transition matrix
- P = probabilities of being in each regime
- A_est = column space of factors in each regime
- B_est = complement of column space of factors in each regime
- path = estimated path of latent state variable
- mu_est = estimated mean of data for each regime

This paper mainly focused on financial data, and did not apply anything to macroeconomic data. 

One of the main (limitations) of this paper is that the estimated states are quite volatile and switch a lot. The paper itself presents the estimated states using rug plots (essentially one dimensional histograms). This seems to be OK for financial data (actually is it?), but is quite problematic for macroeconomic data.

Crucial notes about interpretation

The factor space is assumed to completely change in different regimes. This may or may not be reasonable.

As a nice bonus, you can separately look at each regime. E.g. the first factor explain x% of the variation in regime 1, but only y% in regime 2.

##### INFERENCE

For Macroeconomics, Impulse Response Functions are very important.

These are essentially, given an external shock to something, what will happen to the system?

This is particularly popular for analysing uncertainty shocks. I.e. shocks to the noise term, or variance to the noise term, and seeing how GDP changes, etc.

The extension of this to DFM, is not so straightforward.
Ben says that something like specifying a law of motion of the variance is necessary in this case.

##### Limitations for Macroeconomics

The estimated regimes switch a LOT. 

Fixing/adjusting this to be smoother is not straightforward because the the estimation of the hidden states is done via the Viterbi algorithm.

The transition probabilities are considered to be constant across the entire sample. This may not be reasonable for economics.

Solutions: 
- allow for time varying transition probabilities
- allow for "smoother" regime switching somehow
