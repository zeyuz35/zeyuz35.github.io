---
id: kUt23sqFAGSJSQ2uvjGg0
title: Draft Ideas
desc: ''
updated: 1638748257952
created: 1638510730694
bibliography: [references.bib]
reference-section-title: References
---

## Background Information

Dynamic Factor Models (DFMs) have become a popular way for practitioners to utilize information from a large panel of macroeconomic time series.

Their popularity has increased due to the relatively recent development of inferential theory which has justified their use in large $T$ and large $N$ settings, also known as "double asymptotics".

Most empirical applications of DFMs have been in the context of forecasting, such as in Factor Augmented Autoregressive (FAAR) models, or Factor Augmented Vector Autoregressive (FAVAR) models. 

There does however, exist a separate strand of literature, which instead tries to interpret the DFM with relation to the economy. It can be argued, that the factor process underlying a DFM can be interpreted as primitive shocks to the economy, themselves driven by factor innovations.

## Limitations

However, the current theory underpinning DFMs assume that there are no structural breaks. In the context of DFMs, I define a structural break as being any one, or combination of:

1. a break in the intercept of $X_{it}$
2. a break in the factor loadings $\lambda_i$, i.e. $\lambda_{i}$ is actually time varying, such that 
$\lambda_{i} = 
\begin{cases} \lambda_{i, 1} \quad t \lt t^*\\
\lambda_{i, 2} \quad t > t^*
\end{cases}$
3. a break in the idiosyncratic component $e_{it}$
4. a break in the factor process, which can be from either:

    - a break in the factor dynamics and/or
    - a break in the factor innovations $\eta_t$

Estimation of DFMs and related methods in the presence of breaks has been of great interest, as much empirical work relies on the the assumptions for DFMs not being violated in order to be valid. 

A most topical example is the estimation of $r$, the number of static factors in a DFM, as this is directly necessary for subsequent applications, such as deciding how many factors to put into a FAVAR forecasting model.

## Small breaks vs Big breaks

We first clarify the difference between small breaks and big breaks, as 

[@stock_forecasting_2002] initially show that as $h_{NT} = O(T^{-1})$, then the factor estimates are still consistent. 

[@bates_consistent_2013] subsequently provides the most comprehensive study of the behaviour of the PCA estimator of DFMs, subject to various structural breaks, and loosens this assumption substantially. 

They show that as long as the breaks in the loadings are "small", defined as:

then the convergence rate of the PCA estimator will not be affected, and it suffices, at least theoretically, to ignore any such small breaks when working with the PCA estimator.

It is important to note however, that the work done conducted by [@bates_consistent_2013] focused on theoretical implications for forecasting, and they explicitly show that the[@bai_determining_2002] IC is asymptotically biased in some of these parameterizations which are classified as small breaks. 

Indeed, for some application of DFMs such as data on asset returns, or estimation via state space methods, knowledge of the no. of factors is of direct concern. Hence, they remark that more work is needed to establish necessary conditions for consistent estimation for th eno. of factors.

## 

Many empirical papers have noted that $r$, as estimated by various methods, tends to be a. unstable over time, and b. generally increasing. 

Recent literature has shown that under certain types of structural breaks, the number of factors naively estimated by IC without consideration for breaks can be overestimated.

Specifically, the case of structural breaks in the loadings has been extensively studied via the use of so called "equivalent representation theorems", which show that a DFM with a structural break in the loadings can be equivalently represented as a static model, but with possible more factors, which are called "pseudo factors".

Under such structural breaks where an appropriate representation theorem can be applied, any method estimating the number of factors will instead be consistent for the number of pseudo-factors. 

However, a all papers in the literature thus far have only considered and developed representation theorems for the case of structural breaks in the loadings. Indeed, all setups in the literature have explicitly assumed that the factor process itself is stationary over time, a concern that is pointed out by [@stock_chapter_2016]. 

The behaviour and power of various tests for breaks in loadings against such breaks is unknown. 

## Model Setup



## Proposal







