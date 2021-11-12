---
id: T4FN6sDHfA9wxiZ7Dg5WX
title: Dynamic Factor Models
desc: ''
updated: 1636686615124
created: 1634214992986
geometry: margin=2cm
bibliography: [references.bib]
reference-section-title: References
---

## Nomenclature

This thesis will refer to these as *dynamic* factor models, as opposed to *static* factor models. Confusingly, they are also referred to by [@forniGeneralizedDynamicFactorModel2000] as *Generalized* Dynamic Factor Models. 

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

Subsequently, [@forniGeneralizedDynamicFactorModel2000] and [@forni 2004] study the properties of this algorithm, and establish inferential results for the resulting common component estimator. Dyanmic PCA is shown to provide piecewise consistent estimation of the component as $N$, $T$ increase, and in their followup, this consistency holds if $N, T \rightarrow \infty$ and $N/T \rightarrow 0$, suggesting that some caution to be exercised in finite samples if $N$ is large relative to $T$.

Side note: Ben is not sure how often people actually estimate factor models via this method. Trudging through the literature, it seems that this strand was very exciting for a while, but either no one understood it well enough, or it had other significant limitations that no one actually uses it in applied research. In either case, it does not seem like a viable future path.

Note that because DPCA does not yield a consistent estimator of the common component

Forni's one sided filter approach....

Note that the


## Dynamic PCA

Note that this is VERY intensive!
Also, outputs don't make too much sense... Need to spend more time studying this

Beware of other misnomers in the literature! Someone else somewhere referred to dynamic PCA as simply PCA but run on lagged regressors - this is very different to what the rest of the literature at large says!

freqdom package

Will need to investigate how Barigozzi's factorcpt (which has been archived on CRAN for not passing checks) works.

## Dynamic PCA with Periodic Correlation

pcdpca package
Need to spend time to play around with this.

## Generalized Dynamic PCA

gdpc package (fucking mess)

Methods etc are all broken and even the example code given does not work - no idea how this was approved on CRAN


