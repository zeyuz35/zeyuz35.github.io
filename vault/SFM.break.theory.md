---
id: Nm1KrUYBazwT5ytD11Cre
title: SFM Break Theory
desc: ''
updated: 1638257921885
created: 1635403256841
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
\newcommand{\rank}[1]{\operatorname{rank} \left( #1 \right) }

## Bates et al (2013)

[@bates_consistent_2013] is the first (and only) paper which establishes specified conditions on how large structural breaks can be allowed to be, without affecting the consistency of PCA. As such, it can be viewed in general as an attempt to see how far the original Bai and Ng regularity conditions can be loosened.

Basically, breaks are considered to be "small" and not affect the consistency rate of the PCA esitmator if:

1. The break affects a fraction of series that is decreasing as $N \to \infty$
2. 

Note that the focus here is on the *consistency of PCA*, and *not* how how various different tests would necessarily pick up on this. For example, it is entirely possible that there are "breaks" which are picked up by various tests, but these breaks are sufficiently small enough that they *do not* affect the consistency of the PCA estimator. 

However, that this paper was produced before the development of the equivalent representation theorem, and as such is less useful is determining the precise behaviour of what happens in the presence of a structural break.

They achieve this by focusing on the error term in the usual DFM model setup:
$$
X_{it} = \lambda_{it}' F_t + e_{it},
$$
where $\lambda_{it}$ is allowed to be possibly time varying. The authors re-parameterize the cumulative drift in loadings as 

$$
\Lambda_t - \Lambda_0 = h_{NT} \xi_t,
$$
where $h_{NT}$ is a deterministic scalar that may depend on $N$ and/or $T$. Subbing this back into the general setup yields:
$$
\begin{aligned}
X_t &= \Lambda_t F_t \\
&= \Lambda_0 F_t + e_t + h_{NT}\xi_t \\
X_t &= \Lambda_0 F_t + e_t + w_t
\end{aligned}
$$


[@bates_consistent_2013] focus on three specific examples which are thought to be of particular interest.

1. White noise: all $\xi_{it}$ are i.i.d. across $i$ and $t$, and $\Lambda_t$ is simple $\Lambda_0$ plus some uncorrelated noise.

2. Random walk: The $\xi_{it}$ are each random walk processes, and as such the factor loadings each evolve over time as uncorrelated random walks.

3. Single large break: The $\xi_t$ is simply a sudden shift parameter:
$$
\xi_t = 
\begin{cases}
0 \quad \text{for regime 1} \\
\Delta \quad \text{for regime 2},
\end{cases}
$$
where $\Delta$ is the shift parameter. Note that this case corresponds exactly to the type of break considered by [@breitung_testing_2011], which can be retroactively classified as being observationally equivalent to the emergence of r new factors, and hence results in a a DFM with double the number of factors.

The precise assumptions required on $h_{NT} \xi_t$ are detailed below. Notation here is quite overwhelming: $i, j$ denote cross sectional indices, $s, t$ denote time indices, $p, q$ denote factor indices. 

There exist envelope functions $Q_1(N, T), Q_2(N, T), Q_3(N, T)$ such that for all $N, T$ and factor indices $p_1, q_1, p_2, q_2, \dots r$:

1. $sup_{s, t \leq T} \sum_{i, j = 1}^{N} |E(\xi_{isp_1}, \xi_{jtq_1}, F_{sp_1}, F_{tq_1})| \leq Q_1(N, T)$

2. $sup_{s, t = 1} \sum_{i, j = 1}^{N} \sum_{i, j = 1}^{N} |E(\xi_{isp_1}, \xi_{jsq_1}, F_{sp_1}, F_{sq_1}, F_{tp_2}, F_{tq_2})| \leq Q_2(N, T)$

3. $sup_{s, t = 1} \sum_{i, j = 1}^{N} \sum_{i, j = 1}^{N} |E(\xi_{isp_1}, \xi_{jsq_1}, F_{sp_1}, F_{sq_1}, F_{tp_2}, F_{tq_2})| \leq Q_2(N, T)$

## Baltagi et al

Not the focus of their paper, but [@baltagi_identification_2017] re-visit Bates et al's conditions and are able to subsequently loosen it further a bit.

