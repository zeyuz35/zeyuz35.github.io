
Frequency domain approaches to time series were initially borne out of signals processing. This exists mainly because there exists some tools from that strand of literature which have spilled over into econometrics, namely dynamic principal components.

Most of this is taken from Time Series Analysis and Its Applications by Shumway and Stoffer.

The pioneer of this field is Brillinger - who has written textbooks on this subject.

## Motivation

In some times series, it can be argued that the regularity of a series can be best expressed in terms of periodic variations on the underlying phenomenon which produced said series. 

An important part of this literature is the investigation and exploitation of the properties of the time invariant linear linear filter. 

Note that depending on the series, sometimes many frequency scales will exists. For example, daily observations of a time sereis may exhibit weekly, monthly and quarterly cycles simultaneously.

## Cycles

A cycle is defined as one complete period of a sine or cosine function defined over a unit time interval.

$$
x_t = Acos(2 \pi \omega t + \phi)
$$

for $t = 0, \pm1, \pm2, \dots$ where $\omega$ is the frequency index, $A$ is the amplitude, and $\phi$ is the phase, which determines the start point of the wave function (similar to a horizontal intercept).

It is easier to use a trignometric identity and write this instead as

$$
x_t = U_1 cos(2\pi \omega t) + U_2 sin(2 \pi \omega t)
$$
where $U_1, U_2$ are often taken to be normally distributed random variables. It can be shown that $A = \sqrt(U_1^2 + U_2^2)$. 

Note that this can be further generalized to multiple terms, periodicities and frequencies.

## Estimation

Note that for any time series $x_1, \dots x_n$ where $n$ is odd, it is possible to decompose it into cosine terms.

This can be achieved via Fast Fourier Transforms.

## Spectral Density

Recall that the Wold decomposition justified the use of linear regression for times series.

The spectral representation theorem justifies the use of decompoisition into periodic components proportion to their variances.

Any time series can be shown to have equivalent representation:

$$
\begin{align}
\gamma(h) &= \sigma^2 cos(2 \pi \omega_0 h) \\
&= \frac{\sigma^2}{2}e^{-2 \pi i \omega_0 h} + \frac{\sigma^2}{2}e^{2 \pi i \omega_0 h} \\
&= \int_{-1/2}^{1/2} e^{2 \pi i \omega h} dF(\omega)
\end{align}
$$
where 
$$
F(\omega) = \begin{cases}
0 \quad &\omega < -\omega_0\\
\sigma^2 / 2  \quad &-\omega_0 < \omega < \omega_0\\
\sigma^2 \quad \ &\omega > \omega_0
\end{cases}
$$
$F(\omega)$ behaves like a cumulative distribution function for a discrete random variable, except that $F(\infty) = \sigma^2 = var(x_t)$ instead of 1. $F(\omega)$ is thus a cumulative distribution function of variances, not of probabilities, and is therefore known as the *spectral distribution function*.

The spectral distribution function and autocovariance function express the same information. The autocovariance function expresses total variance as a sum over all lags, whereas the spectral distribution function expresses total variance as an integration over all cycles.

## Estimation

The sample periodogram is a sample estimate of the population spectral density. 

## Eigenvalues and Eigenvectors of Spectral Density Matrices

Pulled from Brillinger textbook.

## Band pass Filters

Band pass filters are used to extract the business cycle component in economic time series. This can reveal the expansions and contractions in economic activity. 

Some people have used band pass filters in order to get a filter variable which has its business cycle frequencies (fluctuations) removed, then run something else, say PCA on the filtered variables. This intuitively estimates PCA and factor analysis, but removes the potentially confounding effects of business cycles.
