
## Bates et al (2013)

Bates et al is the first (and only) paper which establishes specified conditions on how large structural breaks can be allowed to be, without affecting the consistency of PCA. As such, it can be viewed in general as an attempt to see how far the original Bai and Ng regularity conditions can be loosened.

Note however, that this paper was produced before the development of the equivalent representation theorem, and as such is less useful is determining the precise behaviour of what happens in the presence of a structural break.

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
X_t = \Lambda_t Ft = \Lambda_0 F_t + e_t + h_{NT}\xi_t F_t = \Lambda_0 F_t + e_t + w_t
$$


Bates et al focus on three specific examples which are thought to be of particular interest.

White noise: all $\xi_{it}$ are i.i.d. across $i$ and $t$, and $\Lambda_t$ is simple $\Lambda_0$ plus some uncorrelated noise.

Random walk: The $\xi_{it}$ are each random walk processes, and as such the factor loadings each evolve over time as uncorrelated random walks.

Single large break: The $\xi_t$ is simply a sudden shift parameter:
$$
\xi_t = 
\begin{cases}
0 \quad \text{for regime 1} \\
\Delta \quad \text{for regime 2},
\end{cases}
$$
where $\Delta$ is the shift parameter. Note that this case corresponds exactly to the type of break considered by Breitung and Eickmeier, which can be retroactively classified as being observationally equivalent to the emergence of r new factors, and hence results in a a DFM with double the number of factors.

The precise assumptions required on $h_{NT} \xi_t$ are detailed below. Notation here is quite overwhelming: $i, j$ denote cross sectional indices, $s, t$ denote time indices, $p, q$ denote factor indices. 

There exist envelope functions $Q_1(N, T), Q_2(N, T), Q_3(N, T)$ such that for all $N, T$ and factor indices $p_1, q_1, p_2, q_2, \dots r$:

1. $sup_{s, t \leq T} \sum_{i, j = 1}^{N} |E(\xi_{isp_1}, \xi_{jtq_1}, F_{sp_1}, F_{tq_1})| \leq Q_1(N, T)$

2. $sup_{s, t = 1} \sum_{i, j = 1}^{N} \sum_{i, j = 1}^{N} |E(\xi_{isp_1}, \xi_{jsq_1}, F_{sp_1}, F_{sq_1}, F_{tp_2}, F_{tq_2})| \leq Q_2(N, T)$

3. $sup_{s, t = 1} \sum_{i, j = 1}^{N} \sum_{i, j = 1}^{N} |E(\xi_{isp_1}, \xi_{jsq_1}, F_{sp_1}, F_{sq_1}, F_{tp_2}, F_{tq_2})| \leq Q_2(N, T)$

## Baltagi et al

Not the focus of their paper, but Baltagi et al re-visit Bates et al's conditions and are able to subsequently loosen it further a bit.

