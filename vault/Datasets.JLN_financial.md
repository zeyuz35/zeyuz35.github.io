---
id: aeRLPLhAQFy8PWqRNmTpG
title: JLN Financial Data
desc: ''
updated: 1637889198485
created: 1637882328657
bibliography: [references.bib]
reference-section-title: References
---

[@jurado_measuring_2021].

## Macroeconomic dataset

Previously, this was complicated to set up, but as of recently, this is actually just the FREDMD data.

## Financial Dataset

This is more complicated to set up, and I cannot seem to find an up to date version of this set of data series available.

However, it is possible to build this yourself. 

The data is at a monthly frequency. All returns and spreads are expressed in logs (log of gross return or spread), are displayed in percent (multiplied by 100), and annualized by multiplying by 12. 

Essentially, if $x$ is the original return or spread, then the data is transformed first via $1200ln(1 + x/100)$. This is confirmed to match up with the data they give - transform data FIRST using this approach! THEN apply the transformations they suggest.

Federal Reserve data is annualized by default, and therefore not re-annualized. 

This comprises of the following sources:

### Kenneth French

- Fama French Factors (originally 3, expand to 5 factor set)
- 25 portfolios formed on Size and Book to Market (5 x 5).
    - From this, series R15-R11 is obtained, which is the spread between small (small, high boot to market) and (small, low book to market) portfolios
- Momentum Factor: from this
    - we obtain the series UMD, which IS the momentum factor
- 49 Industry portfolios
    - Use all value-weighted series, exclusing any series that have missing observations
    - obtain series Agric through Other
    - Omitted series are Soda, Hlth, FabPr, Guns, Gold and Softw (may not be reasonable, add them in?)
- 100 Portfolios formed in Size and Book to Market
    - Use all value weighted series, excluding any series that have missing observations
    - Results in X_Y naming scheme, X stands for index of size variable (1, 2, ... 10) and Y stands for index of book to market variable (Low, 2, 3, ... 8, 9, High)
    - Omitted series are 1_low, 1_3, 7_high, 9_9, 10_8, 10_9, 10_high

Notice how all of these are using value weighted series - this may not be the most reasonable, but this is because Kenneth French only provides value weighted portfolios...

### CRSP

Value weighted and dividend data were obtained from CRSP. Using Annual Update data, obtian monthly value weighted returns series:

- vwretd (with dividends)
- vwretx (ex dividends)

A normalized price series is then constructed as:

$$
P_0 = 1\\
P_t = P_{t - 1}vwretx
$$

A dividend series can then be constructed as:

$$
D_t = P_{t - 1}(vwretd_t - vwretdx_t)
$$

A de-seasoned dividend series is then constructed using the moving average over the entire year:

$$
D_t^* = \frac{1}{12} \sum_{j = 0}^{11} D_{t - j}
$$

Price and dividends assuming reinvestment (of dividends) is calculated using:

$$
P_0^{re} = 1 \\
P_t^{re} = P_{t - 1} vwretd_t
$$

Similarly, dividends from the scheme can also be reconstructed:

$$
D_{t}^{re} = P_{t - 1}^{re} (vwretd_t - vwretx_t)
$$

As before, dividends from this are de-seasoned with a moving average:

$$
D_{t}^{re, *} = \frac{1}{12} \sum_{j = 0}^{11}D_{t - j}^{re}
$$

The final 5 data series are constructed as:

1. $D_log(DIV) = \Delta log(D_t^*)$
2. $D_log(P) = \Delta log(P_t)$
3. $D_DIVreinvest = \Delta log (D_{t}^{re, *})$
4. $D_Preinvest = \Delta log (P_t^{re})$
5. $d-p = log(D_t^*) - log(P_t)$

### Cochrane - Piazzesi factors

https://www.johnhcochrane.com/bond-risk-premia





