
## Resources for getting paths working

https://www.randigriffin.com/2017/04/25/how-to-knit-for-mysite.html

https://nb.balaji.blog/posts/pandoc-extract-images/

https://stackoverflow.com/questions/41604263/how-do-i-display-local-image-in-markdown

https://gist.github.com/cben/46d9536baacb7c5d196c/



## Matrix Algebra



## Linear Models

Notation

![](./assets/images/2021-11-16-11-50-24.png)

Assumptions/regularity conditions

![](./assets/images/2021-11-16-11-49-32.png)

Useful matrix algebra identity 

![](./assets/images/2021-11-16-11-52-12.png){max-width=80%}

### FWL Theorem

![](./assets/images/2021-11-16-11-53-34.png)

### Statistical Properties of OLS

![](./assets/images/2021-11-16-11-54-19.png)

Proof of variance of residuals

![](./assets/images/2021-11-16-11-55-20.png)

### Inference

The very basic case

![](./assets/images/2021-11-16-11-57-55.png)

![](./assets/images/2021-11-16-11-58-12.png)

More generally

![](./assets/images/2021-11-16-11-59-07.png)

Restricted Least Squares (Lagrange Approach)

![](./assets/images/2021-11-16-12-00-06.png)

Note the choice of choosing the lagrange multiplier to has a constant in front to simplify things!

![](./assets/images/2021-11-16-12-00-24.png)

### Chow test

Normal derivation

![](./assets/images/2021-11-16-12-01-39.png)

![](./assets/images/2021-11-16-12-03-37.png)

Alternative derivation when one of the sub samples has less observations than regressors:

![](./assets/images/2021-11-16-12-04-18.png)

![](./assets/images/2021-11-16-12-04-50.png)

This is an F test with (T - T2 - k) = (T1 - k) dof and T2 indicator variables (restrictions).

![](./assets/images/2021-11-16-12-05-05.png)

## Likelihood

KL divergence. Note that the relative orders of the thetas are reversed in the fraction. 

![](./assets/images/2021-11-16-12-08-00.png)

This proof is straightforward, but tedious. Focus on a case of n = 2. Just expand out the multiplication, etc.

![](./assets/images/2021-11-16-12-09-05.png)

Remember that log(x) is concave, and -log(x) is convex.

### Notation

The support function is the loglikelihood

The score is the 1st derivative of the loglikelihood

The hessian is the 2nd derivative of the loglikelihood

The fisher information is the expected value of the outer product of the score

Under certain conditions, the fisher information is also negative expected value of the hessian

### Conditions

MLE estimator itself *exists*.

In practical terms, need to check that:

1. loglik is continuous and differentiable wrt theta
2. loglik is bounded (finite)
3. limits of loglik, and check that this crosses over 0 (implies a turning point, and hence existence)

Alternatively, use the second derivative directly:

![](./assets/images/2021-11-16-12-11-09.png)

If the parameter space is convex, and loglik is concave (negative 2nd derivative), then the MLE *exists* and is *unique* (note that uniqueness impliex existence).

![](./assets/images/2021-11-16-12-13-54.png)

### Statistical Properties of MLE

![](./assets/images/2021-11-16-12-15-34.png)

Easy way to check that some *unbiased* estimator reaches the CRLB. 

![](./assets/images/2021-11-16-12-16-39.png)

Practically, in the case of MLE, K(theta) can actually be *any* arbitrary function of theta, as noted by Casella and Berger, pg 364.

![](./assets/images/2021-11-16-12-18-14.png)

#### OLS MLE

![](./assets/images/2021-11-16-12-18-59.png)

![](./assets/images/2021-11-16-12-19-15.png)

### Asymptotic Properties

General distribution of MLE:

![](./assets/images/2021-11-16-12-20-20.png)

Note that the information matrix relies on *true* theta0, so instead use i(theta hat) as a consistent estimator for it.

### Inference

Restrictions are denoted

![](./assets/images/2021-11-16-12-21-52.png)

#### Wald Test

![](./assets/images/2021-11-16-12-22-06.png)

Proof: 1st order Taylor Expand h(theta hat) about true theta 0

#### LM/Gradient Test

![](./assets/images/2021-11-16-12-23-11.png)

The proof in the notes has typos. 

#### Likelihood Ratio (criterion differnce) test

The easiest one!

![](./assets/images/2021-11-16-12-23-43.png)

Proof is harder, requires 2nd order Taylor Series expansion. 

## Stochastic Order



## Generalised Method of Moments

Note that Method of Moments is too easy and skipped (not too exciting).

There are p parameters, and k moment conditions

The true moment conditions are denoted by h, s.t. E(h) = 0

The sample moment conditions are denoted by m, whose sample (empirical) means correspond to E(h)

![](./assets/images/2021-11-16-12-45-57.png)

![](./assets/images/2021-11-16-12-46-15.png)

GMM is identified if:

![](./assets/images/2021-11-16-12-48-01.png)

### Asymptotics

![](./assets/images/2021-11-16-12-48-44.png)

![](./assets/images/2021-11-16-12-48-53.png)

The proof is a straightforward, by tedious Taylor Series expansion about m(theta hat)

Relative Efficiency

![](./assets/images/2021-11-16-12-49-43.png)

![](./assets/images/2021-11-16-12-49-57.png)

### Weighting matrix

A an efficient weighting matrix needs to chosen up to a proportionality:

![](./assets/images/2021-11-16-12-50-40.png)

In practice, is it easier to directly work out the variance of the moment conditions and get the standard efficient weighting matrix.

However, the previous result is useful, as this allows us to be sloppy with constants (e.g. missing Ts).

#### OLS

Worked example

![](./assets/images/2021-11-16-12-52-19.png)

#### IV Regression

Worked Example. Note that sometimes Don is sloppy and specifies different T proportionalities.

![](./assets/images/2021-11-16-12-53-28.png)

![](./assets/images/2021-11-16-12-53-44.png)

#### MLE

Worked Example


### Inference

#### J Test (test oof overidentifying restrictions)

![](./assets/images/2021-11-16-14-47-51.png)


#### Notation

![](./assets/images/2021-11-16-14-48-21.png)

![](./assets/images/2021-11-16-14-48-33.png)
#### Wald Test

![](./assets/images/2021-11-16-14-48-48.png)

This has a typo, the variance should not be inverted.

#### LM/Gradient Test

![](./assets/images/2021-11-16-14-49-25.png)

#### Criterion Difference Test

Again, the easiest one!

![](./assets/images/2021-11-16-14-49-45.png)


#### Min Chi Squared Test

![](./assets/images/2021-11-16-14-50-29.png)

It can be shown that Min Chi Square and Criterion Dfference test are the same (unsurprisingly)
#### Auxiliary Moment Tests

![](./assets/images/2021-11-16-14-51-26.png)

![](./assets/images/2021-11-16-14-51-44.png)

![](./assets/images/2021-11-16-14-51-58.png)

![](./assets/images/2021-11-16-14-52-13.png)

#### Conditional Moment Test
## Extremum Estimators

### M Estimators

Extremum estimators which minimize a sample average criteron are called M estimators.
## Censoring and Truncation



### Truncated

A *truncated* distribution is where any observations exceeding some threshold are not observed at all.

### Censored

A *censored* distribution is where any observations exceeding some threshold are simply recorded as that threshold, but its actual value is unknown (censored).



## Generalised Linear Models (GLMs)

![](./assets/images/2021-11-16-14-40-06.png)

Common exponential family:

![](./assets/images/2021-11-16-14-40-21.png)

A more general definition of this is given:

![](./assets/images/2021-11-16-14-41-23.png)

Take special note of the cumulant generating function for the sufficient statistic:

![](./assets/images/2021-11-16-14-41-39.png)

This is actually also given in Don's notes, though not so clearly

![](./assets/images/2021-11-16-14-42-54.png)

GLMs are estimated by MLE, with the following asymptotic properties

![](./assets/images/2021-11-16-14-45-00.png)

### Deviance

![](./assets/images/2021-11-16-14-45-50.png)

![](./assets/images/2021-11-16-14-46-13.png)

Pearson Residual

![](./assets/images/2021-11-16-14-46-36.png)

