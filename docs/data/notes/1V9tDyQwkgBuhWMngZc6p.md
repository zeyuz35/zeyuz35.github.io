
## Central Limit Theorem

## Law of Large Numbers

There are different sets of sufficient conditions for the WLLN.

1. Kolmogorov, all X are i.i.d. with finite expectation. Note that this implies the SLLN.
2. Chebyshev, all X are uncorrelated, such that the variance is finite, and the sample variance converges to 0 asymptotically
3. All X have finite variance, and sample variance converges to 0 asymptotically. Additionally, all sample covariances, and the sum of all sample covariances are finite (looser version of the Chebyshev version).

## Slutsky/Continuous Mapping Theorem

1. If $X_n \overset{as}{\rightarrow} X$, $f(X_n) \overset{as}{\rightarrow} f(X)$
2. If $X_n \overset{p}{\rightarrow} X$, $f(X_n) \overset{p}{\rightarrow} f(X)$
3. If $X_n \overset{d}{\rightarrow} X$, $f(X_n) \overset{d}{\rightarrow} f(X)$

Part 3 is called the Continuous Mapping Theorem. Part 1 is called Slutsky's Theorem.

However, both can be referred to as the Continuous Mapping Theorem, because Slutsky's Theorem is a really just a special case of the broader CMT.

Note that the above is a very simplified version! To get the more complicated versions which we typically apply, you will need to define $f()$ in a special way, e.g. $f(X) = X + Y$ where $Y$ is some other random variable.

## Cramer-Wold Device

## 