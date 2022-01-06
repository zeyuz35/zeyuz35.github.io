---
id: Eao3HsBMWoKOJ6YjwKV1u
title: Literature Review
desc: ''
updated: 1641359879020
created: 1641256729309
bibliography: [references.bib]
reference-section-title: References
---

\newcommand{\sumT}{\sum_{t = 1}^{T}}
\newcommand{\sumTs}{\sum_{s = 1}^{T}}
\newcommand{\sumN}{\sum_{i = 1}^{N}}
\newcommand{\sumNj}{\sum_{j = 1}^{N}}
\newcommand{\convp}{\overset{p}{\to}}
\newcommand{\convd}{\overset{d}{\to}}
\newcommand{\limN}{\lim_{N \to \infty}}
\newcommand{\limT}{\lim_{T \to \infty}}
\newcommand{\plimT}{\operatorname{plim}_{T \to \infty}}
\newcommand{\plimN}{\operatorname{plim}_{N \to \infty}}
\newcommand{\plimNT}{\operatorname{plim}_{N,T \to \infty}}
\newcommand{\ceil}[1]{\left \lceil #1 \right \rceil }
\newcommand{\floor}[1]{\left \lfloor #1 \right \rfloor }
\newcommand{\sumTfloor}{\sum_{t = 1}^{\floor{\tau T}}}
\newcommand{\sumTfloort}{\sum_{t = \floor{\tau T + 1}}^{T}}
\newcommand{\rank}[1]{\operatorname{rank} #1 }

We begin by providing a broad overview of the literature thus far.

## Exact Factor Models

A factor model for a $T \times N$ panel of time series $X$ assumes that $X$ is generated from lower dimensional factor structure:

$$
X_{it} = \lambda_{it}' F_t + e_{it} \\
X_t = \Lambda_t F_t + e_t \\
X = F \Lambda' + \mathbf{e}.
$$ which correspond to the individual, time slice, and whole panel representations respectively.

An exact factor model assumes that the idiosyncratic shocks $e_{it}$ do not have any serial correlation or cross sectional correlation, a strict assumption that is unrealistic for empirical applications.

## Approximate Factor Models

The *exact* factor model can be subsequently loosened to an *approximate* factor model, in the sense that the idiosyncratic shocks are now allowed to have a limited degree of serial and cross sectional correlation.

An approximate factor model has the *static* representation if the factors $F_t$ can only affect $X_t$ directly, and not through its lags:

$$
X_t = \Lambda F_t + e_t
$$

The above formulation is to be contrasted with the dynamic form of the dynamic factor model, where the factors themselves are allowed to evolve dynamically:

$$
X_{it} = \lambda_i'(L) f_t + e_{it}
$$

where $\lambda_{i}'(L) = (1 - \lambda_{1i}L - \dots - \lambda_{is}L^s)$ is a vector of dynamic factor loadings or order $s$. We focus on a finite $s$, in contrast to the separate strand of literature focused on *generalized* dynamic factor models which allows $s$ to be infinite (see [@forni_generalized_2000] and later section for a short review). In either case, the factors themselves are allowed to evolve according to:

$$
f_t = C(L)\epsilon_t
$$

where $\epsilon_t$ are $q \times 1$ $i.i.d. errors, which can be interpreted as the *primitive shocks* in an economic model. The literature which focuses on these primitive shocks refers to $q$ as the number of *dynamic* factors.

The dynamic factor model with $q$ *dynamic* factors can always be re-written as a static factor model with $r$ *static* factors, where $r$ is finite. More generally, $q \leq q(s + 1) = r$, because $F_t$ will contain the leads and lags of $f_t$. 

It is because of this relationship that the literature usually does not explicitly differentiate between the two, referring (somewhat confusingly) to both the Static Factor Model and Dynamic Factor Model as simply Dynamic Factor Models, with the former referred to as the *static representation* of the Dynamic Factor Model when necessary. 

Empirically, it has been noted that forecasting approaches using either formulation perform rather similarly. However, for the purposes of interpretation such as the identification of primitive shocks, distinction is important. 

### Generalized Dynamic Factor Models

In a separate, but related literature, [@forni_generalized_2000] develop so the called *Generalized* Dynamic Factor Model (GDFM) in which $s$ is explicitly allowed to $\to \infty$. Estimation and analysis of this model instead focuses on the spectral density of $X$.

However, this approach is noticeably more complicated, and is still subject to its own issues, such as increased computational intensity, and the necessity of formulating a "one-sided" filter in order to reliably estimate the factors towards the end of the sample for forecasting purposes.

It is perhaps due to these difficulties that in spite of the dynamic factors as estimated via spectral analysis have been shown to have good performance by its authors, that the applied forecasting literature has, at large, stuck to using traditional static factor models, usually as estimated via the principal components estimator. 

## Latent Factor Models

More recently, [@lam_estimation_2011] develop and formulate the *Latent* Factor Model (LFM). 

The key difference in this formulation is that serial correlation in the error term is explicitly allowed for, and in fact, *required* to achieve identification. Estimation of the factors and loadings is done via applying an eigendecomposition of the empirical autocovariance matrices of the data. 

@lam_factor_2012 subsequently develop the inferential theory for the number of *latent* factors. 

Although there has been some work done with this model as a basis, (see [@liu_regime-switching_2017, @liu_threshold_2020, @liu_estimating_2022]), in general, this has not proven to be a popular way to estimate factor models. 

The precise relationship between this latent factor model with the existing literature is an unanswered question. 

## Structural Breaks in DFMs

The topic of structural breaks in the context of Dynamic Factor Models has received much attention recently.

Due to simplicity, almost all of the literature thus far has focused on the the Dynamic Factor Model as estimated (statically) via the PC estimator.

### Small Changes in Factor Loadings

We first make a preliminary note that there exists a necessary distinction between so called "small" and "large" breaks in dynamic factor models. Heuristically, the estimation of $F_t$ via the principal components estimator is not affected asymptotically if the breaks in the factor loadings is "small". @bates_consistent_2013 establish the conditions under which the changes in $\Lambda$ can be ignored for the estimation of $F_t$. They consider the following formulation:

$$
X_{it} = \lambda_{it}' F_t + e_{it}, \; i = 1, \dots, N, t = 1, \dots, T.
$$

where $\lambda_{it}$ is now allowed to be time-varying. Define $\Lambda_t = (\lambda_{1t}, \dots, \lambda_{Nt})'$ and let the initial factor loading $\Lambda_0$ be fixed. The factor loading at time $t$ is then allowed to evolve over time according to:

$$
\Lambda_t = \Lambda_0 + h_{NT}\xi_t
$$

where $h_{NT}$ is a deterministic scalar allowed to depend on $N, T$, $\xi_t = (\xi_{1t}, \dots, \xi_{Nt})'$ is an $N \times r$ stochastic process which governs the dynamics of $\Lambda_t$. 

Combining the above, we have:

$$
X_{t} = \Lambda_0 F_t + h_{NT}\xi_t F_t + e_{t}.
$$

@bates_consistent_2013 treat $h_{NT}\xi_t F_t + e_{t}$ as the combined idiosyncratic error for the factor model, and develop conditions under which the combined idiosyncratic error does not affect the consistency of the PCA estimator $\widehat{F}$ in @bai_determining_2002. Although a rigorous set of conditions on $h_{NT}$ is provided, for brevity, we provide the three most empirically relevant cases as derived by @bates_consistent_2013

Example 1 White Noise: $h_{NT}$ are i.i.d. across all $i, t$ and $E||\xi_{it}||^4 \lt \infty$. If $h_{NT} = O(1)$, then consistency holds.

Example 2 Random Walk: $h_{NT}$ are random walk processes, i.e. $\xi_{it} = \sum_{s = 1}^{t} \zeta_{is}$, where $\zeta_{is}$ are i.i.d. across all $i, t$ and $E||\xi_{it}||^4 \lt \infty$. A sufficient condition for consistency is $h_{NT} = o(T^{-1/2})$. Heuristically, this means that as long as the factor loading innovations shrink sufficiently fast enough, then PCA will not be affected.

Example 3 Single Large Break: let $\delta_i \in \mathbb{R}^r$ be a shift parameter. Then assume that the factor loadings are subject to a one time shift:

$$
\xi_{it} = \begin{cases}
0_{r \times 1} \; &t = 1, \dots, \floor{\pi_0 T} \\
\delta_i \; &t = \floor{\pi_0 T} + 1, \dots, T.
\end{cases}
$$
If $h_{NT} = O(1)$ *and* at most $O(N^{1/2})$ series undergo a break, then PCA is still consistent. Example 3 is perhaps the most directly relevant case in the analysis which follows. Heuristically, PCA is still consistent as long as the break affects a shrinking fraction of all series asymptotically, and the their sizes are fixed. 

It is important to note that the above conditions are stated only for the consistency of $F$, and *not* for the number of factors, which in general *is* affected even by the presence of small breaks. It is for this reason that a more recent strand of literature has emerged, focusing on the detection of small breaks to facilitate accurate estimation of the number of factors can be accurately determined before and after possible *small* breaks (see @bai_estimation_2020 and @duan_quasi-maximum_2021 forthcoming). 

In what follows, we focus on *large*, one time breaks (Example 3) in dynamic factor models.

## Model Setup and Notation

We focus on the case of *large*, one time breaks in dynamic factor models. To begin, we consider the singular break case in the factor loadings within the static model notation as proposed by @han_tests_2015:

$$
X_{it} = \begin{cases}
F_{0, t}' \lambda_{0, i} + F_{1, t}' \lambda_{1, i} + e_{it}\ \quad \text{for} \quad t = 1, \dots, \floor{\tau T} \\
F_{0, t}' \lambda_{0, i} + F_{1, t}' \lambda_{2, i} + e_{it}\ \quad \text{for} \quad t = \floor{\tau T} + 1, \dots, T,
\end{cases}
$$
where $F_{0, t}$ is a $(r - q) \times 1$ vector of time invariant factors, $F_{1, t}$ is a $q \times 1$ dimensional factor whose loadings undergo structural change.

The matrix representation of the the previous setup is:

$$
\begin{aligned}
X &= 
\begin{bmatrix}
F^{0, 1} \Lambda_0' + F^{1, 1} \Lambda_1' \\
F^{0, 2} \Lambda_0' + F^{1, 2} \Lambda_1'
\end{bmatrix} + e \\
&= \begin{bmatrix}
F^{0, 1} & F^{1, 1} & 0 \\
F^{0, 2} & 0 & F^{1, 2}
\end{bmatrix} 
\begin{bmatrix} \Lambda_0 & \Lambda_1 & \Lambda_2 \end{bmatrix}' + e \\
&= \mathcal{F} \Theta + e.
\end{aligned}
$$

Note that the number of factors above is possible larger than $r$, and depends on the rank of $\Theta$. In general, $r \leq \rank{\Theta} \leq r = q$ and $\rank{\Theta}$. [@han_tests_2015] further classify breaks into 3 different types:

1. $rank(\Theta) = r$, Type 1 Break

The changes in $\lambda_{1, i} - \lambda_{2, i}$ need to be so idiosyncratic across $i$ such that $\Lambda_1$ and $\Lambda_2$ are linearly independent. The type of breaks in loadings considered by @breitung_testing_2011 corresponds to a Type 1 Break.

2. $r \lt rank(\Theta) \lt r + q$, Type 2 Break

The column rank of $[\Lambda_1 : \Lambda_2]$ is $q$, so that there exists a $q \times q$ matrix $Z_0$ such that $\Lambda_2 = \Lambda_1 Z_0$. 

A type 2 break implies that the "break" is simply a rotation or scaling of the existing loadings. The practical interpretation of a type 2 break is that *all* loadings change in a homogeneous way. It is remarkable that type 2 changes can be interpreted as either a change in the common dynamic factors, or a homogeneous change in all factor loadings - it is not possible to separately identify the two cases. 

Although @han_tests_2015 allow $Z_0$ is allowed to be singular, in which case there will be emerging (disappearing) factors after the break, we further distinguish the singular case, as it turns out that different tests can treat this in a distinctly different way. 

Type 2a: $Z_0$ is singular

The singular transformation case is the most topical for practical applications, as people tend to be interested in emerging or disappearing factors. 

Type 2b: $Z_0$ is non-singular

The non-singular case corresponds to the more general case where factors have their loadings changed in a homogeneous way across *all* series. Although ruled out by @han_tests_2015's regularity assumption, this in fact more generally corresponds to the case where there is a break in the dynamic factors, such as a change in the dynamic factor loadings, or a change in factor variance. 

3. $rank(\Theta) = q$, Type 3 Break

A type 3 break is simply any combination of both a type 1 and type 2 break, which arises out of technical necessity. 

Although @breitung_testing_2011's test does legitimately identify and test for a break in the factor loadings from the factor dynamics, it does not generalise to the entire cross section of data. This is because in the approximate model setup, the idiosyncratic shocks are allowed to have (a limited degree of) serial and cross sectional correlation, making it invalid to simply pooled these tests, and additionally, $N \to \infty$, which results in difficulties in establishing valid asymptotics.

@chen_detecting_2014, @han_tests_2015 and @baltagi_identification_2017 propose tests for structural breaks in the factor loadings. However, because breaks in the factor loadings and factor dynamics are in general not separately identifiable, they all assume, as an identification condition that the factors are are stationary before and after the break (have the same variance). @han_tests_2015 and @baltagi_identification_2017 both formulate Equivalent Representation Theorems, which state that PCA will estimate an equivalent factor model with time invariant loadings, but with all breaks in the loadings transmitted to the estimated pseudo factor space. Based on this, they formulate a est statistic based on the second moments process of the pseudo factors.

However, procedures based on the pseudo factors cannot be accurately stated to be a test against breaks in factor loadings, because breaks in the pseudo factors may be in fact due to any combination of the following:

1.  breaks in the loadings and/or
2.  breaks in the factor dynamics and/or
3.  breaks in the factor innovations.

The identification assumption of stationary factors explicitly rules out points 2 and 3, even though the distinction and resulting interpretation in the differences between these cases are different. @stock_chapter_2016 in their review chapter on Dynamic Factor Models remarks that many of these tests are new, and may have power against breaks in the factor dynamics as well.

In our following simulation study, we investigate the performance and properties of these tests in various cases.

@ma_estimation_2018 provides a methodology to identify breaks in the loadings without assuming stationary factors. However, their method does not allow for a differing number of factors across regimes. More importantly, their method, being motivated via the LASSO literature, requires the specification of hyperparameters, and is very sensitive to this arbitrary choice. Practically, and it is unclear how to choose these for outside of synthetic data, as results are very non-robust. 

## Disentangling Breaks in Factor Loadings and Breaks in Factor Dynamics

The below table summarises available tests. Yes means that the 

|Test | Type 1 | Type 2a | Type 2b | Type 3 | Notes |
------|------- | --------|---------|--------|-------|
| @breitung_testing_2011 | Yes* | n/a | n/a | n/a | Only for single series $i$
| @chen_detecting_2014 | Yes | Yes* | No | Yes* | Test statistic has power against Type 2a, but no theoretical result
| @han_tests_2015 | Yes | Yes | Yes | Yes | Cannot distinguish between different types
| @baltagi_identification_2017 | Yes | Yes | Yes | Yes | Cannot distinguish between different types
| @baltagi_estimating_2021 | Yes | Yes | Yes | Yes | Cannot distinguish between different types
| @bai_estimation_2020 | Yes | No | Yes | Yes | Cannot distinguish between different types
| @bai_estimation_2020 | Yes | No | Yes | Yes | Cannot distinguish between different types

Thus, ignoring the separability issue, the problem of disentangling the breaks in factor loadings and those in factor dynamics can be be reduced down to the same problem as distinguishing between the different *types* of breaks. 

Our goal is to propose a methodology that is able to detect all types of breaks, as well as classify *which* type of break they are, in order to pin down the precise source of the break (at least up to the separability constraint).

@chen_detecting_2014 provides the closest methodology is achieving this - their method has power against type 1 and type 2a breaks and no power against type 2b breaks - however, the asymptotics of their statistic has only been formally established for type 1 breaks. 

It is also remarkable that another possible way to disentangle the breaks follows the remark by @chen_detecting_2014 - type 2b breaks do never augment the estimated factor space with more factors, and a method based on the estimated number of factors before and after the break compared to the full sample may be possible. We do not pursue this method, because it has been noted that estimators of the number of factors are sensitive to even small breaks, and empirically, are often in disagreement with one another. 

## Proposed Procedure

We propose a two step procedure in order to identify which kind of break, and therefore disentangle the source of the break.

The intuition behind our procedure is motivated by the fact that a type 2b break affects *all* series in a very homogeneous way. Noting that this sort of break can be detected via existing methods, in the absence of other sorts of breaks, it stands to reason then that a simple estimate of long run variance for each series, averaged over the entire cross section will yield an estimator for the factor variance. 

As a first step procedure, we propose to "standardize" the data by the inverse of this estimate of the factor variance. The resulting data should therefore not exhibit any "breaks" induced by changes in factor dynamics.

This adjusted data then satisfies the piecewise stationary factors identification condition (which was unreasonable) that existing methods assume, and thus these can then used as the second step in a 2 stage procedure to disentangle the breaks.

## Simulation Setup

We consider 9 different simulation specifications to explore how different types of breaks are handled by different tests.

1. Null Case - no breaks

The first experiment contains no breaks and thus acts as a control.

$$
X_{it} = F_{t}' \lambda_{i} + e_{it}\ \quad 
$$

where $F_t$ is a $(3 \times 1)$ vector of static factors, and each $\lambda_i \sim i.i.d. N(0_3, I_3)$.

2. Idiosyncratic Break in Factor Loadings (Type 1)

$$
X_{it} = \begin{cases}
F_{t}' \lambda_{1i} + e_{it}\ \quad \text{for} \quad t = 1, \dots, \floor{\tau T} \\
F_{t}' \lambda_{2i} + e_{it}\ \quad \text{for} \quad t = \floor{\tau T} + 1, \dots, T,
\end{cases}
$$

where $\lambda_{1i} \sim i.i.d. N(0, I_{N \times r})$, which changes to $\lambda_{2i} \sim i.i.d. N(0, I_{N \times r})$.

3. Break in Factor Dynamics (Type 2b)

$$
\begin{aligned}
X_{it} &= 
f_t' \lambda_{i} + e_{it}, \\
f_t &= \begin{cases}
\rho_1 + f_{t - 1} + \epsilon_{t}\ \quad \text{for} \quad t = 1, \dots, \floor{\tau T} \\
\rho_1 + f_{t - 1} + 2\epsilon_{t}\ \quad \text{for} \quad t = \floor{\tau T} + 1, \dots, T,
\end{cases}
\end{aligned}
$$
where the factor variance (via the innovations) undergoes a break. This corresponds to hetereoskedasticity in the underlying factors.

4. Break in Factor Loadings and Factor Dynamics (Type 3)

$$
X_{it} = \begin{cases}
F_{t}' \lambda_{1i} + e_{it}\ \quad \text{for} \quad t = 1, \dots, \floor{\tau T} \\
F_{t}' \lambda_{1i} + e_{it}\ \quad \text{for} \quad t = \floor{\tau T} + 1, \dots, T,
\end{cases}
$$



5. Common Break in Factor Loadings (Type 2b)

All factor loadings are assumed to undergo the *same* type of break. This is mathematically identical to a break in factor dynamics.

$$
X_{it} = \begin{cases}
F_{t}' \lambda_{1i} + e_{it}\ \quad \text{for} \quad t = 1, \dots, \floor{\tau T} \\
F_{t}' (2\lambda_{1i}) + e_{it}\ \quad \text{for} \quad t = \floor{\tau T} + 1, \dots, T,
\end{cases}
$$
in which the factor loadings are all multiplied by the same constant after the break. 

6. Common Break in Idiosyncratic Error

$$
X_{it} = \begin{cases}
F_{t}' \lambda_{i} + e_{it}\ \quad \text{for} \quad t = 1, \dots, \floor{\tau T} \\
F_{t}' \lambda_{i} + 2e_{it}\ \quad \text{for} \quad t = \floor{\tau T} + 1, \dots, T,
\end{cases}
$$
where the "break" is now in the idiosyncratic error term. 

7. Break in Factor Autocorrelation (Type 2b)

$$
\begin{aligned}
X_{it} &= 
f_t' \lambda_{i} + e_{it}, \\
f_t &= \begin{cases}
\rho_1 + f_{t - 1} + \epsilon_{t}\ \quad \text{for} \quad t = 1, \dots, \floor{\tau T} \\
\rho_2 + f_{t - 1} + 2\epsilon_{t}\ \quad \text{for} \quad t = \floor{\tau T} + 1, \dots, T,
\end{cases}
\end{aligned}
$$
where $\rho_1 = 0.7$, $\rho_2 = 0.3$. Clearly, a change in the autocorrelation coefficient of the factor process will also change the factor variance.

8. Appearance of Extra Factor Lag (Type 2a)

$$
X_{it} = \begin{cases}
F_{t}' \lambda_{1i} + e_{it}\ \quad \text{for} \quad t = 1, \dots, \floor{\tau T} \\
F_{t}' \lambda_{2i} + e_{it}\ \quad \text{for} \quad t = \floor{\tau T} + 1, \dots, T,
\end{cases}
$$

9. Disappearing Factor (Type 2a)

$$
X_{it} = \begin{cases}
F_{t}' \lambda_{1i} + e_{it}\ \quad \text{for} \quad t = 1, \dots, \floor{\tau T} \\
F_{t}' \lambda_{2i} + e_{it}\ \quad \text{for} \quad t = \floor{\tau T} + 1, \dots, T,
\end{cases}
$$

### Simulation Results

We present the results of the simulation study.

Unsurprisingly, 

Perhaps most interesting is the result of @chen_detecting_2014's test statistic, which seems to exhibit power against Type 2a breaks. However, the distribution of their test statistic under such breaks has not been formally derived. 

## Empirical Study

To date, there is limited empirical work conducted on the detection of structural breaks in dynamic factor models, although there is a consensus that there are structural instabilities that exist. This is due to a number of reasons:

1. Possibility of multiple breaks

Most of the literature thus far has only considered the case of a single break, but the empirical data may be subject to multiple breaks. Although it is well known that single break tests do have power against multiple breaks, the finite sample performance of such tests is notorious for being unreliable, in the sense that they do not always agree which break is the biggest.

2. Possibility of non-smooth breaks

It is also well known in the structural break literature that structural break tests may perform poorly when instead of large sudden breaks, the DGP instead exhibits small, smooth changes over time. @su_time-varying_2017 and @su_testing_2020 show in simulation evidence for this, and propose a non-parametric framework to estimate and test for smooth changes. However, their method cannot distinguish between smooth changes and sudden changes.

3. Lack of data in the $T$ dimension

The previous two points compound the main issue of there not being enough data in each subsample. This issue is profound in the structural break literature - whether using the framework proposed by @andrews_tests_1993 or @bai_estimating_1998, the resulting test statistics are poorly behaved towards the start and end of the subsample, and hence a proportional of the data, denoted by $\epsilon$, usually around 0.1 or 0.15, is needed to trimmed from both the start and end. 

These problems often mean that practically, a practitioner must be careful of making sure that the sample is large enough to avoid boundary issues, but also not large enough that it may include another possible break. As such, the practitioner must have a pre-existing idea of where such breaks may occur already, and "pre-treat" the data accordingly beforehand.

Popular breaks that are typically suggested and/or identified by the literature are:

- Great Moderation, early 1980s
- Dot-com bubble, early 2000s
- GFC, late 2007/early 2008
- COVID pandemic, late 2019/early 2020

It is remarkable that a large amount of the earlier literature identified the Great Moderation as a potential break date, but this may due to the data from the 2000s onwards being trimmed out due to lack of data back then.

### Data 

#### Stock and Watson 2005

#### Stock and Watson 2009

#### Stock and Watson 2012

#### FREDMD

@mccracken_fred-md_2015 provides a large, monthly frequency, macroeconomic database based on US data. This is emerged in more recent times to be the *de facto* standard for large empirical macroeconomic databases, and is aimed to be broadly compatible and equivalent to the vintages prepared by Stock and Watson.

Any series with missing observations 

#### FREDQD

@mccracken_fred-qd_2020 provides a large, quarterly frequency, macroeconomic database based on US data - the quarterly counterpart to FREDMD. 



### Empirical Results

## Future Work

The work presented thus far has identified notable gap in the literature, namely disentangling 

It remains as future work to formally prove and establish the asymptotic validity of the proposed procedure. 

It is noteworthy that the procedure bears some resemblance to the Feasible Generalised Principal Components estimator proposed by @choi_efficient_2012. 


### Timeline

