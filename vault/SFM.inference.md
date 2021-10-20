---
id: LvkZzWN557soKo2Cg4JAc
title: inference
desc: ''
updated: 1634735327257
created: 1634735273785
---

# Inference for SFM

## Inference for PCA Estimator

Chamberlain and Rothschild introduce the first *approximate* factor models, which allow for the relaxation of the covariance of the errors terms.

Bai and Ng (2002) and Bai (2003) subsequently develop the inferential theory for the principal components estimator 
asd


Assumptions 1-4 are sufficient for the consistent estimation for the factors, their loadings, and the number of factors.

In what follows below, $||A|| = [tr(A'A)]^{1/2}$ denotes the Frobenius norm.

1. Factors

$$
\newcommand{\sumT}{\sum_{t = 1}^{T}}
\newcommand{\convp}{\overset{p}{\rightarrow}}
%%
\begin{aligned}
E||F_t^0|| < \infty \\
\frac{1}{T} \sumT F_t^0 F_t^{0 \prime} \convp \Sigma_F (r \times r) p.s.d.
\end{aligned}
$$

This assumption allows $F_t$ to be dynamic such that $A(L)F_t = \epsilon_t$, but does not allow the dynamics to enter into $X_{it}$ directly, and is therefore still a static relationship.

2. Factor Loadings  

$$
\newcommand{\sumT}{\sum_{t = 1}^{T}}
\newcommand{\convp}{\overset{p}{\rightarrow}}

\begin{aligned}
|| \lambda_i || \leq \bar{\lambda} \leq \infty,
|| \Lambda^{0 \prime} \Lambda^0 / N - \Sigma_N|| \convp 0, \Sigma_N = (r \times r) p.s.d
\end{aligned}
$$
This ensures that each factor has a non-trivial contribution to the variance of $X_{it}$. The loadings are allowed to be random in this simple setup, provided that they are independent from the factors and idiosyncratic errors, and $E||\lambda_i || ^4 \leq M$.

3. Time and cross-sectional dependence and hetero-skedasticity

$$

$$

4. Weak dependence between factors and idiosyncratic errors

Assumptions 5-8 are then further introduced by Bai to develop the asymptotic distribution and therefore inference for the estimated factors and loadings. Note that 

5. 
6. 
7. 
8. 

These make up the total 8 assumptions/regularity conditions, typically referred to as the Bai and Ng regularity conditions, and are considered standard in the literature.
