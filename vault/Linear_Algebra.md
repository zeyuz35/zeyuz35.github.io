---
id: dailP0MR8nIVqoelobEaN
title: Linear Algebra
desc: ''
updated: 1636283703044
created: 1635165273731
---

A document containing useful matrix algebra results for reference.

## Other Results



## Eigenvalues and Eigenvectors

Eigenvalues and Eigenvectors are only defined for square matrices. 

The no. of non zero eigenvalues corresponds to the rank of the matrix.

## Singular Value Decomposition

The generalisation of eigendecompositions to rectangular (non square) matrices.

Typically not used in the factor literature too much, and more so in the machine learning literature.

For our purposes, it can be shown that an SVD of a square matrix is equivalent to an eigendecomposition. 

That is, the left and right matrices as given by an SVD will be identical and correspond to the eigenvectors, and the middle 

## Principal Components Analysis

The principal components are typically calculated by running an eigendecomposition on the variance matrix of some dataset. Normally, datasets are X = N x p with N much larger than p, and so this done via $1/(N - 1)(X'X)$.

However, this is not always the case in macroeconomic data, which instead has the data structure X = T x N, where T and N are of similar dimensions (although typically $T > N$, $N > T$ when quarterly/yearly data is used). In accordance with Bai and Ng's review chapter on DFMs, $XX'$ is the "tilde" normalization, and $X'X$ is the "bar" normalisation. In the literature, both are used depending on the model setup (one can be easier to work with than the other), but the "tilde" nroamlisation tends to be more common.

Note that in R, $X'X$ is the same as crossprod(), and $XX'$ is the same as tcrossprod(). The former options are preferred for readability in general, even though they are slightly slower.

In terms of saving on computational costs, whichever option which results in a covariance matrix of smaller dimensions is preferred, though asymptotically the theoretical results for either are the same.

It should be noted that there is a lack of sign identification for the eigenvectors - each eigenvector is observationally equivalent to its negative. The eigenvalues themselves are not affected by this. For this reason, it is helpful and common to fix the signs, typically such that the first element of each eigenvector is positive. This is what the current implementation does by default.

Although eigen() is the traditional backend, the algorithm behind this is considered to be numerically unstable and a bit outdated, particularly when there is very high multicollinearity. As such, the machine learning community tends to prefer using SVD on the covariance matrix instead of eigen, as this tends to be numerically more stable and faster. SVD is a generalisation of eigen for rectangular matrices, and can be shownt o be identical when the matrix is symmetric (covariance matrix).

princomp() is usually the implementation preferred, as this provides an OOP interface with other useful methods, such as projecting new data using the decomposition. However, these extra features are typically not needed in macroeconomic analysis, so a much simpler interface using just eigen() or svd() is used instead.

