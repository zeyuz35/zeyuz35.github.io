
## Barigozzi et al JoE

Implemented in `factorcpt` package, which is quite basic, and needs to be installed via archive because it has been abandoned by its authors.

This is the first comprehensive treatment of high-dimensional times series factor analysis with multiple change points.

Note that a presence of a structural break implies that the data is *not* stationary, but rather, *piecewise stationary*. 

Note that Cheng et al concerns single change point analysis in the loadings and number of factors.

Ma and Su considers changes in the loadings only - not sure how this would work.

## Summary of Method

1. Input time series and an arbitrary number of factors
2. for each number of factors, iterate
3. Estimate PCA on the data the usual way, and yield an estimate of the common component and idiosyncratic error
4. The cmmon components and erorrs are separately transformed into panels with almost piecewise constant signals via wavelet based transformations g() and h()
5. Run a Double CUMSUM BInary Segmentation and stationary bootstrap procedure on the panels estimated, to get estimates of the changepoints

## Framework

Despite the name, they work within the framework of a *static* factor model. That is, the loadings and the number of factors both remain static and unchanging.

This is because according to the authors, representation theorems are developed enough that *any* unstable model can be represented as an equivalent static model (not entirely true, especially at the time of their publication)

## Important note on Bai and Ng estimator

Barigozzi recall that Han and Inoue (Proposition 1) and Chen et al (Proposition 2) show that BNIC achieves asymptotic consistency for estimating r, in the presence of ONE break in the loadings. However, such an approach tends to exhibit very poor finite sample performance when the errors are both serially and cross-sectionally correlated, or when the signal to noise ratio is low. It is also noted that the performance heavily depends on the penalty term, and the relative magnitudes of N and T.

Barigozzi's approach depends heavily on an accurate estimate of r, and without it, it may lead to failure to detect change points.

Their approach is to allow over specification of numebr of factors, but used a modified version of PCA, which essentially "caps" the contributions of the last few eigenvectors.

## Wavelets

This is new content for me!

Nason et al proposed the use of wavelets as a way to decompose any non stationary time series analagous to Fourier exponentials in classical representations for statonary processes.

Wavelet periodogram and cross-periodgram sequences of the the wave decompositions have been shown to have their expectations have a one to one correspondence to the second oreder structure of the input time series.

The gist of this is, any jump in the variance and cross covariance strcutures of X is translated to a jump in the mean of its wavelet periodogram and cross-periodogram sequences. 

## Double CUSUM

