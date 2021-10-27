---
id: T4FN6sDHfA9wxiZ7Dg5WX
title: Dynamic Factor Models
desc: ''
updated: 1635315524154
created: 1634214992986
---

This section details (truly) dynamic factor models. 

Stock and Watson denote t a truly dynamic factor model as follows:

$$
X_{it} = \lambda_i (L)'f_t + e_{it}
$$

where $f_t$ is a $q$ dimensional vector of dynamic factors, also known as primitive shocks, and $\lambda_i(L)'$ denotes the $q$ dimensional lag polynomial, also called the "dynamic factor loadings".

Recall that the principal components estimate is formulated to estimate the *static* factors, which are written as 

$$
X_t = \Lambda F_t + e_t
$$

For more details on the PC estimator, see [[SFM]] and its related sections.

Estimating the dynamic factors directly has proven to be difficult, and is done mainly via dynamic principal components. Static principal components finds the closest approximation of the covariance matrix of $X_t$, among all covariance matrices of reduced rank. In contrast, dynamic principal components finds the closest approximation to the *spectrum* of $X_t$, among all possible spectral density matrices of reduced rank.

Originally, Brillinger (1981)'s estimation algorithm generalizes static PCA to the frequency domain. The spectral dentisy of $X_t$ is first estimated via some consistent spectral density estimator $\widehat{S}_{XX}(\omega)$, at a given frequency $\omega$. Next, the eigenvectors corresponding to the $q$ largest eigenvalues of this matrix are computed. Then, an inverse Fourier Trasform of these eigenvectors yields estimators of the principal component time series using the formulas given. 

Note that because this was originally developed for classical factor analysis, the asymptotics of this under a large $N$ dimension were not developed by the original author, though as expected asymptotic normality results hold.

Subsequently, Forni et al (2000, 2004) study the properties of this algorithm, and establish inferential results for the resulting common component estimator. Dyanmic PCA is shown to provide piecewise consistent estimation of the component as $N$, $T$ increase, and in their followup, this consistency holds if $N, T \rightarrow \infty$ and $N/T \rightarrow 0$, suggesting that some caution to be exercised in finite samples if $N$ is large relative to $T$.

Note that because DPCA does not yield a consistent estimator of the common component

Forni's one sided filter approach....

However, because factor can be allowed to have its own dynamics, DFMs can also be expressed more explicitly:

$$

$$

Note that the


## Dynamic PCA

freqdom package
## Dynamic PCA with Periodic Correlation

pcdpca package

## Generalized Dynamic PCA

gdpc package (fucking mess)

Methods etc are all broken and even the example code given does not work.

