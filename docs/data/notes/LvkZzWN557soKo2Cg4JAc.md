
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

## High Level Overview

See [[LSE]] notes for a broader, high level interpretation of these. In summary, a set of valid regularity conditions requires that:

1. The factors to be *pervasive*, i.e. have non-negligible effects on most of the variables
2. The idiosyncratic components to be *weakly* cross-correlated

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

Under these 4 assumptions, [@bai_determining_2002] show that the PCA estimator $\widehat{F}_t$ is able to consistently estimate the true factors up to an arbitrary rotation:

$$
\frac{1}{T} \sumT ||\widehat{F}_t - H'F_t|| = O_P(\delta_{NT}^{-2})
$$
where $\delta_{NT} = \operatorname{min}({\sqrt{T}, \sqrt{N}})$, $H = (\Lambda' \Lambda/N)(F' \widehat{F}/T)V_{NT}^{-1}$, and $V_{NT}$ is a diagonal matrix consisting of the first $r eigenvalues of $XX'/NT$ in descending order.

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

This assumption allows the number of strongly correlated errors to grow at a rate slower than $\sqrt{N}$. Note that the last two parts are basically CLTs. 

7. The eigenvalues of $\Sigma_\Lambda, \Sigma_F$ are distinct. 

These make up the total 7 assumptions/regularity conditions, typically referred to as the Bai and Ng regularity conditions.

### PCA Asymptotics

Let:

- $V = \plimNT V_{NT}$
- $Q = \plimNT \frac{\widehat{F}_t' F}{T}$

Under the previous 7 assumptions, [@bai_critical_2003] shows that:

1. Asymptotic Normality of Factors. If $\sqrt{N}/T \to 0$, then for each $t$
$$
\sqrt{N}(\widehat{F_t} - H' F_t^0) = V_{NT}^{-1} \left( \frac{\widehat{F}' F}{T} \right) \frac{1}{\sqrt{N}} \sumN \lambda_i e_{it} + o_p(1) \\
\convd N(0, V^{-1} Q \Gamma_t Q' V^{-1})
$$

2. Asymptotic Normality of loadings. If $\sqrt{T}/N \to 0$, then for each $i$
$$
\sqrt{T}(\widehat{\lambda_i} - H^{-1}\lambda_i) = \left( \frac{\widehat{F}_t' F}{T} \right) \left( \frac{\Lambda' \Lambda}{N} \right) \frac{1}{\sqrt{T}} \sumT F_t e_{it} + o_p(1) \\
\convd N(0, Q^{-\prime} \Phi_i Q^{-1})
$$

3. Asymptotic Normality of Common Component. 

Note that because $N$ and $T$ are likely to be similar to in size to one another in practice, both of the above results are likely to hold, and the above distributions are regarded as good approximations in good samples.

### PCA Identification

Confusingly, due to the multiplicative structure of $F \Lambda'$, there is a notable identification issue: $FA (\Lambda A^{-1})'$ are observationally equivalent for any arbitrary non-singular $A$ matrix. Because of this, at least $r^2$ restrictions need to be imposed to separately identify the $F$ and $\Lambda$.

PCA implicitly imposes the following identification schemes:

1. $\widehat{F}_t' \widehat{F}/T = I_r$, and $\widehat{\Lambda}' \widehat{\Lambda}$ is diagonal. This corresponds to the "tilde" normalisation. The estimated factors are set to $\sqrt{T}$ times the eigenvectors corresponding to the eigenvalues of $XX', T \times T$

2. $\widehat{\Lambda}_t' \widehat{\Lambda}/N = I_r$, and $\widehat{\F}' \widehat{\F}$ is diagonal. This corresponds to the "bar" normalisation. The estimated factors are set to $\sqrt{N}$ times the eigenvectors corresponding to the eigenvalues of $X'X, N \times N$.

In order to deal with the possible structural breaks, several authors bring in:

8. Identification condition for structural changes in factor loadings

$$
T^{-1} \sumTfloor F_t F_t' \convp \tau \Sigma_F \\
T^{-1} \sumTfloort F_t F_t' \convp (1 - \tau) \Sigma_F
$$
Note that we have used $\tau$ instead of $\pi$, as some other authors do. 

## Bai and Ng 2006

[@bai_confidence_2006] derive additional convergence rates for the PC estimator. Notably, due to the convergence rates derived, they show that it is OK to treat the estimated factors as subsequent regressors.

This is mostly relevant for formally justifying the use of estimated factors in a subsequent regression, say a FAVAR model.

## Barigozzi Assumptions

[@barigozzi_simultaneous_2018] instead follows the strand of literature in the *generalized* dynamic factor models (truly dynamic) and uses an alternative set of assumptions.

For the most part, these are very similar.

For practical purposes, it does not matter which set - simply choose whichever one is easier for the problem at hand.

