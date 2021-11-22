---
id: LvkZzWN557soKo2Cg4JAc
title: Static Factor Model Inference
desc: ''
updated: 1637545170363
created: 1634735273785
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

## High Level Overview

See [[LSE]] notes for a broader, high level interpretation of these. (Will try to merge these together).



## Bai and Ng Regularity Conditions

[@bai_determining_2002] develop the following 4 assumptions required for the estimation of the number of static factors. These are considered to be fairly standard assumptions within the literature. 

Assumptions 1-4 are sufficient for the consistent estimation for the factors, their loadings, (up to an arbitrary rotation) and the number of factors.

In what follows below, $||A|| = [tr(A'A)]^{1/2}$ denotes the Frobenius norm.

1. Factors (Assumption F)

$$
E||F_t^0|| < \infty \\
\frac{1}{T} \sumT F_t^0 F_t^{0 \prime} \convp \Sigma_F (r \times r) p.s.d.
$$

This assumption allows $F_t$ to be dynamic such that $A(L)F_t = \epsilon_t$, but does not allow the dynamics to enter into $X_{it}$ directly, and is therefore still a static relationship. 

It is in essence a moment condition ensuring that each factor has non-trivial contribution to the variance of $X_{it}$. Note that the true factors $F_t^0$ are assumed to be *stationary*.

2. Factor Loadings  

$$
|| \lambda_i || \leq \bar{\lambda} \leq \infty, \\
|| \Lambda^{0 \prime} \Lambda^0 / N - \Sigma_N|| \convp 0, \Sigma_N > 0, (r \times r)
$$

Similarly, this ensures that each factor has a non-trivial contribution to the variance of $X_{it}$. The loadings are allowed to be random in this simple setup, provided that they are independent from the factors and idiosyncratic errors, and $E||\lambda_i || ^4 \leq M$. 

3. Time and cross-sectional dependence and hetero-skedasticity

a. $E(e_{it}) = 0, E|e_{it}|^8 < M$
b. $E(e_{it} e_{js}) = \sigma_{ij, ts}, \\ 
|\sigma_{ij, ts}| \leq \bar{\sigma_{ij}} \forall (t, s), \\
|\sigma_{ij, ts}| \leq \tau_{ts} \forall (i, j)$, such that:

- $1/N \sum_{i, j = 1}^N \bar{\sigma_{ij}} \leq M$, 
- $1/T \sum_{t, s = 1}^N \tau_{ts} \leq M$,
- $1/NT \sum_{i, j, t, s = 1} |\sigma_{ij, ts}| \leq M$

4. Weak correlation between Factors and Errors

$E(1/N \sumN ||T^{-1/2} \sumT F_t e_{it}) ||^2 \leq M$

[@bai_inferential_2003] then further develop/supplement the previous 4 assumptions with the following, in order to develop the *asymptotic* behaviour of the PCA estimator for the factors and their loadings. Note that because the previous 4 assumptions can already achieve consistency of the PCA estimator (which is what most people care about anyway), the following 4 assumptions are not as well used.

5. Strengthening of Assumption 3 earlier. 

For all $t \leq T$, $i \leq N$, $\sumTs |\tau_{s, t}| \leq M$, and $\sumN |\bar{\sigma_{ij}}| \leq M$

Note that under time series and cross sectional independence, both parts of this assumption are already implied.

6. Moments and Central Limit Theorem

-  $E|1/\sqrt{N} \sumN [e_{is} e_{it} - E(e_{is} e_{it})] |^4 \leq M$ for all $(t, s)$

- The $r \times r$ matrix satisfies
$$
E|| \frac{1}{NT} \sumT \sumN F_t \lambda_k' e_{kt}|| \leq M
$$
- For each $t$, $1/\sqrt{N} \sumN \lambda_i e_{it} \convd N(0, \Gamma_t)$ as $N \to \infty$, where 
$$
\Gamma_t = \limN \frac{1}{N} \sumN \sumNj E(\lambda_i \lambda_j' e_{it} e_{jt}).
$$
- For each $i$, $1/\sqrt{T} \sumT F_t e_{it} \convd N(0, \Phi_i)$ as $T \to \infty$, where:
$$
\Phi_i = \limT 1/T \sumTs \sumT E(F_t^0 F_s^{0 \prime} e_{is} e_{it})
$$

7. The eigenvalues of $\Sigma_\Lambda, \Sigma_F$ are distinct. 

This assumption allows the number of strongly correlated errors to grow at a rate slower than $\sqrt{N}$. Note that the last two parts are basically CLTs. 

These make up the total 7 assumptions/regularity conditions, typically referred to as the Bai and Ng regularity conditions.

## Bai and Ng 2006

[@bai_confidence_2006] derive additional convergence rates for the PC estimator. Notably, due to the convergence rates derived, they show that it is OK to treat the estimated factors as subsequent regressors.

This is mostly relevant for formally justifying the use of estimated factors in a subsequent regression, say a FAVAR model.

