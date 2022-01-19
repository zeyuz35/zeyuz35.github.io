---
id: MsmFdXyWfizd5g8GGcObD
title: Covariance Weighted Forecasting
desc: ''
updated: 1641804621913
created: 1636095097255
bibliography: [references.bib]
reference-section-title: References
---

## Literature Review

To our knowledge, the closest works to our proposed methods are @; however, their focus can be more accurately described as using a GMM based approach to estimate and conduct inference for mixture models, in the context of conditional variance forecasting.



## Model Setup and Notation

We assume that the true model $\mathcal{M}$ with corresponding true parameters $\theta^*$ generates new data $y_{t+1}$ via some complex function $f(\theta^*; \mathcal{F}_t)$, where $\mathcal{F}_t$ denotes a filtration up to and including time $t$. Let there be $k$ candidate models under consideration $M_1, \dots, M_k$. Each model has a corresponding $\theta^{(k)}_0$ "pseudo-true" parameters, which are the parameter values that will yield the model that is "closest" to the true model, each with corresponding consistent estimators $\widehat{\theta}^{(k)}_0$. 

Each candidate model produces forecasts for $y_{t + 1}, \dots y_{t + H}$ denoted respectively by $\widehat{f}_{t + 1} (\widehat{\theta}^{(k)}_0; \mathcal{F}_t), \dots, \widehat{f}_{t + H} (\widehat{\theta}^{(k)}_0 \mathcal{F}_t))$, which we suppress as $\widehat{f}_{t + H, k}$ for notational simplicity. We approximate $\mathcal{M}$ via a linear combination of candidate models $\widehat{\mathcal{M}} = \sum_{i = 1}^{k} w_i M_i$, and hence our method is aimed at estimating the set of weights $\mathbf{w} =  (w_1, \dots w_k)'$. Because we aim to make no assumptions on the candidate models themselves, our method is arguably non parametric in nature.

We assume that the true model $\mathcal{M}$ with corresponding true parameters $\theta^*$ is some complex function $f(\theta^*; y_t)$. Our model setup is as follows. 

Let their be $k$ candidate models under consideration $M_1, \dots, M_k$. Each model has a corresponding $\theta^{(k)}_0$ "pseudo-true" parameters, which are the parameter values that will yield the model that is "closest" to the true model, each with corresponding consistent estimators $\widehat{\theta}^{(k)}_0$. Each candidate model produces a corresponding forecast $\widehat{f}_k (\widehat{\theta}^{(k)}_0)$, which we suppress as $\widehat{f}_k$ for notational simplicity. We approximate $\mathcal{M}$ via a linear combination of candidate models $\widehat{\mathcal{M}} = \sum_{i = 1}^{k} w_i M_i$, and hence our method is aimed at estimating the set of $w_i$ weights. Because we aim to make no assumptions on the candidate models themselves, our method is arguably non parametric in nature.

We assume that the true model and data generating process $\mathcal{M}$ with corresponding true parameters $\theta^*$ is some complex function $f(\theta^*; y_t)$. Let there be $k$ candidate models under consideration $M_1, \dots, M_k$. Each model has a corresponding $\theta^{(k)}_0$ "pseudo-true" parameters, which are the parameter values that will yield the model that is "closest" to the true model, each with corresponding consistent estimators $\widehat{\theta}^{(k)}_0$. 

Each candidate model produces forecasts for $y_{t + 1}, \dots y_{t + H}$ denoted respectively by $\widehat{f}_{t + 1} (\widehat{\theta}^{(k)}_0), \dots, \widehat{f}_{t + H} (\widehat{\theta}^{(k)}_0)$, which we suppress as $\widehat{f}_{t + H, k}$ for notational simplicity. We approximate $\mathcal{M}$ via a linear combination of candidate models $\widehat{\mathcal{M}} = \sum_{i = 1}^{k} w_i M_i$, and hence our method is aimed at estimating the set of weights $\mathbf{w} =  (w_1, \dots w_k)'$. Because we aim to make no assumptions on the candidate models themselves, our method is arguably non parametric in nature.

Instead, we aim to restrict assumptions to the *data* and the *losses* of each candidate model. 

## Estimation

We estimate the weights based on the covariance matrix of the loss vectors. Define the loss vector (using MSE) as:
$$
\begin{aligned}
\mathcal{L} =
\begin{bmatrix}
L(M_1) \\
L(M_2) \\
\vdots \\
L(M_k)
\end{bmatrix} = 
\begin{bmatrix}
	\frac{1}{T} \sum_{i = 1}^T (y_i - \widehat{f}_1)^2 \\
	\frac{1}{T} \sum_{i = 1}^T (y_i - \widehat{f}_2)^2 \\
	\vdots \\
	\frac{1}{T} \sum_{i = 1}^T (y_i - \widehat{f}_k)^2
\end{bmatrix}
\end{aligned}
$$

We estimate the weights based on the covariance matrix of the loss vectors. Define the (weighted) loss vector as:

$$
\begin{aligned}
\mathcal{L(\mathbf{w})} = 
\begin{bmatrix}
w_1 L(M_1) \\
w_2 L(M_2) \\
\vdots \\
w_k L(M_k)
\end{bmatrix} = 
\begin{bmatrix}
	w_1 \frac{1}{H} \sum_{h = 1}^H (y_{t + h} - \widehat{f}_{t + h, 1}) \\
	w_2 \frac{1}{H} \sum_{h = 1}^H (y_{t + h} - \widehat{f}_{t + h, 2}) \\
	\vdots \\
	w_k \frac{1}{H} \sum_{h = 1}^H (y_{t + h} - \widehat{f}_{t + h, k})
\end{bmatrix},
\end{aligned}
$$
and its corresponding variance-covariance matrix:
$$
\begin{aligned}
J = 
\operatorname{cov}(\mathcal{L(\mathbf{w})}) =
\begin{bmatrix} 
\operatorname{cov}(L(M_1), L(M_1) & \dots & \operatorname{cov}(L(M_1), L(M_k)) \\
\vdots & \ddots & \vdots \\
\operatorname{cov}(L(M_k), L(M_1) & \dots & \operatorname{cov}(L(M_k), L(M_k)) \\
\end{bmatrix}
\end{aligned}
$$
The weights for each model are then constructed using $J$. Ideally, the weights will be constructed using a scheme that takes into account the correlation between the losses of different models. 

A naive starting point is to simply weight models using the inverse of the diagonal elements of $J$. This way, models with a higher variance in their losses (i.e. less robust) are penalized more and given less weight.

This method is aimed at leveraging a large number of models (i.e. $k \rightarrow \infty$), and hence its implementation may need to use methods from the high dimensional covariance matrix literature, which can be more efficient by exploiting the increasing sparsity as an increasingly number of different models are considered. Note that although our setup looks similar a GMM-type estimator with a vector moment conditions and a quadratic optimization, it is different because the loss vector $\mathcal{L}$ does not have any parameters to be optimized. 

Further note that similar to GMM, our loss vector may be subject to problems of serial correlation, and it is likely to require an intial stage to correct for this, in order to consistently estimate $J$.

The weights for each model are estimated by the minimizing a quadratic loss form:
$$
\begin{aligned}
	\underset{\mathbf{w}}{\operatorname{argmin}} \  \mathcal{L}(\mathbf{w})' \Sigma \mathcal{L}(\mathbf{w})
\end{aligned}
$$ 

subject to the constraints $\mathbf{w} \mathbf{1} = 1$ and $w_i \geq 0$ for all $i$. This can be easily translated into the following quadratic programming form:

$$
\begin{aligned}
\underset{\mathbf{w}}{\operatorname{argmin}} \  \mathcal{L}(\mathbf{w})' \Sigma \mathcal{L}(\mathbf{w})
\end{aligned}
$$
subject to
$$
\begin{aligned}
A' \mathbf{w} = 
\begin{pmatrix}
1 & 1 & \dots & 1 \\
1 & 0 & \dots & 0 \\
0 & 1 & \dots & 0 \\
\vdots & \vdots & \ddots & 0 \\
0 & 0 & \dots & 1
\end{pmatrix}' \geq b_0 = 
\begin{pmatrix}
1 \\
0 \\
\vdots \\
0 \\
0
\end{pmatrix}
\end{aligned}
$$

This method is aimed at leveraging a large number of models (i.e. $k \rightarrow \infty$), and hence its implementation may need to use methods from the high dimensional covariance matrix literature, which can be more efficient by exploiting the increasing sparsity as an increasingly number of different models are considered. 

Further note that similar to GMM, our loss vector may be subject to problems of serial correlation, and it is likely to require an initial stage to correct for this, in order to consistently estimate $\Sigma$.

Under optimal forecasts, the standardized residuals should be a sequence of zero mean.

Additional idea:
Add in the square of the residuals to proxy for the variance. Sometimes the variance of the residuals of different methods may also be correlated, and we wish to control for this. This is done by simply demeaning and squaring the residuals to yield a realized volatility series, which in turn proxies for the latent volatility.

We could introduce further moment conditions based on higher order moments. E.g. realized quadricity to proxy for kurtosis, etc.

## Interpretations

It is possible to cast the proposed methodology within the framework of GMM and use this as a basis for developing further inferential theory. To see this, note the following GMM based setup:

Parameter Vector

Moment Conditions

Notice that due to the moment conditions, the model in this case is exactly specified.

Variance Matrix of Moment Conditions (for asymptotically efficient GMM)

Optimization

Regularity Assumptions

Wheel in some regularity assumptions standard to GMM here

## Testing for validity of extra models

Often, when using 


## Extensions to infinitely many series and models

In the future, we are interested in extending the framework to infinitely many series and/or models, in addition to the standard $T$ asymptotics.

Ideally, one would expect that any new models introduced would introduce less and less information already available. Hence, it is expected that adding more models would eventually add all possible information available for forecasting, and it is from this perspective which we wish to develop asymptotic theory for. 

Note that this introduces notable challenges. The optimization requires the calculation of weights, which involves 1. estimating a covariance matrix of residuals related to the models, and 2. inverting this covariance matrix, both of which are difficult tasks when the dimension is taken to infinity.

## Simulation Study

We conduct a simulation to study the finite sample properties of the proposed procedure. 

### Simulation Design

1. Null Case, AR1

2. Mixture Model

3. Mixture Model

4. Structural Break Model

5. Dynamic Factor Model

6. White Noise

7. Mis specified Case

The goal of this setup is to see what the procedure does when none of the candidate models are correctly specified. Heuristically, we expect that the "closest" model is given all of the weight.

### Results

### Notes

The forecast residuals cannot be too collinear, otherwise this results in a near singularity for the variance matrix. This is subtly different to the models themselves being identical, because it is possible for different models to perform similarly in certain periods of time.



## Empirical Study

We conduct two separate empirical studies to demonstrate the performance of our proposed procedure: inflation forecasting and unemployment forecasting.

### Inflation Forecasting

#### Motivation

#### Data

#### Constituent Models

#### Results

### Unemployment Forecasting

#### Motivation

#### Data

#### Constituent Models

#### Results


### Other Notes

Bruce Hansen made some slides which summarize what has been done so far very nicely...

https://www.ssc.wisc.edu/~bhansen/cfe2021/CFE2021_BruceHansen_Part_2.pdf

Fall back idea

Develop a GMM framework which generalizes what ahs been done in the literature

Notes

Simplexes are spiky, so optimizing over them will tend to set 0 weights on most models
