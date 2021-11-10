
Documents summarizing estimator for $q$, the number of *dynamic* factors.

Note that in general, because truly dynamic factors are very difficult to estimate and work with, it is often the case that these methods will rely on a consistent estimator for the static factors $r$ instead. This has the notable advantages of avoiding likelihoods, Kalman filters, etc.

Truly dynamic factor models tend to be very underdeveloped in general. Stock and Watson note in their more recent handbook chapter that there does not exist a comparison between these methods.

## Amengual and Watson (AW07)



## Bai and Ng (2007) BN07

Bai and Ng work directly with the factor and uise an information criteria to estimate the rank of the residual covariance matrix of a VAR estimated using the r estimated principal components.

There is an implemention in the nowcasting package, which is in the process of being gutted and tailored to our needs.

## Hallin and Liska (2007) HL07

In a completely different approach

Note that this was referenced and used in Ma and Su, although this was entirely understood at the time of reading.


