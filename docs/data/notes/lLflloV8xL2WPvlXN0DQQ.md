
This document contains the specification and implementation of various simulation designs used in the literature to explore structural breaks in dynamic factor models.

In accordance with the literature, all "breaks" are treated as being absorbed into the loadings, due to the loadings and factors being not separately identifiable.

Although this is only meant to house simulation designs, a brief overview of each paper and their limitations is also provided. Thus, for now it serves as a literature review of sorts.

## Model Setup and Notation

Let us define the following three equivalent model notations for dynamic (static) factor models:

$$
X_{it} = \lambda_{it}' F_t + e_{it} \\
X_t = \Lambda_t F_t + e_t \\
X = F \Lambda' + \mathbf{e}.
$$
which correspond to the individual, time slice, and whole panel representations respectively. 

Note that it is the norm in the literature to consider a model setup where all breaks in DFMs are pushed into the loadings, due to the lack of separate identifiable for the factors and loadings. 

However, confusingly, PCA will always estimate a set of factors and loadings assuming that there are *no* structural breaks, i.e. a set of time invariant loadings. As a consequence, because the loadings are forced to be time invariant, breaks are then pushed into the estimated factors, which can manifest as breaks in the so called "pseudo factors", or simply as more factors than is required. 

Both of these consequences are of direct interest to practitioners, as the use of DFMs is typically for the purpose of estimating factors for further regression analysis such as forecasting or as instruments in an IV setting. Ignoring the possibility of structural breaks in the data when estimating factors can thus directly result in having factors which themselves exhibit a structural break, or having to use more factors than is needed. 

## Function objects and methods

This section outlines the technical details of the implementation and data structure that is to be consistently used across all simulation designs. This is necessary so that different designs can be easily be transferrable, and presumably only learning one interface is sufficient for exploring them.

All DFM_sim objects should contain:

-  factors, a $T \times r$ matrix of the simulated factors
-  loadings, a $N \times r \times T$ *array* of potentially time varying factor loadings
-  resid, a $T \times N$ matrix of idiosyncratic error terms
-  fitted, a $T \times N$ matrix of *true* data (i.e. the common component). This is generated by $factors \times loadings$ for each $T$ in the array for loadings
-  data, a $T \times N$ matrix of the simulated, observed data

where all of the above items can be easily accessed with correspondingly named methods.

In general, the data component and method will be the most frequently used. Note that this is NOT scaled, in accordance to what is done in the literature. If one desires scaling, they will need to pass this data item to scale(), or specify data(scale = TRUE). 

They also crucially have an info component, a string indicating which simulation specification it is.

### Extra methods/helpers

One can also directly access the workhorse constructor function to generate fitted values and new simulation objects, given individual components (say from other methods).

This allows one to easily mix and match different specifications.

To generate a new dataset, the constructor function requires three components on a basic level: the array of loadings, array of factors, and array of stochastic errors. An extra name argument is also recommended to help put in extra info.

### Plotting

Some basic plotting methods are provided to help visualize the simulated data. There is a corresponding plot method for each of the items, and these are very similar (if not identical) to the plot methods that are used with the output of static_DFM functions.



# Specifications

Detailed specifications for each simulation specification is included in this section of document. This should be self contained enough, but occasionally extra consultation from the original paper(s) may be necessary.

## Breitung and Eickmeier (2011)

Breitung and Eickmeier are arguably the first authors to consider the possibility of structural breaks in DFMs.

Correspondingly, their simulation specification is very simple.

The data is generates as:
$$
y_{it} = f_t' \lambda_{it} + \epsilon_{it}
$$
where the SINGLE factor $f_t$ is distributed with 0 mean and unit variance, and $e_{it}$ is distributed with distributed with 0 mean and variance $\sigma_{i} \sim U(0.5, 1.5)$. The structural break in the loadings is induced by:
$$
\lambda_{it} =
\begin{cases}
\lambda_i, \quad \text{for} \quad \text{regime 1}, \\
\lambda_{i} + b \quad \text{for} \quad \text{regime 1},
\end{cases}
$$
and $\lambda_i \sim N(1, 1)$. The parameter $b$ therefore measures the size of the break, and values of $b = 0, 0.3, 0.5, 0.7, 1$ are explored. 

BE note that using standard Bai and Ng criteria, the number of pseudo factors is estimated to be $r = 2$ instead of 1. Indeed, as Breitung and Eickmeier have noted, it is true that for that the breaks they consider, the number of pseudo factors is doubled. To see this, we re-write their setup using the framework subsequently developed by Han and Inoue and Baltagi et al:
$$
\begin{aligned}
X &= 
\begin{cases}
\begin{bmatrix}
F_1^0 \Lambda_0' & + & 0 \\
F_2^0(\Lambda_0' + \mathbf{b}) & + & 0
\end{bmatrix} + E
\end{cases} \\
&= \begin{cases}
\begin{bmatrix}
F_1^0 \Lambda_0' & + & 0 \\
F_2^0 \Lambda_0' & + & (F_2^0 \mathbf{b}) I 
\end{bmatrix} + E
\end{cases} \\
&= \begin{cases} 
\begin{bmatrix} 
F_1^0 \Lambda_0' & + & 0 \\
F_2^0 \Lambda_0' & + & F_2^1 I 
\end{bmatrix} + E
\end{cases},
\end{aligned}
$$
where it is clear that the BE setup can be more formally represented equivalently as a an emergence of a extra factors (which are a linear transformation of the original factors) with a corresponding loading matrix that is simply equal to the identity matrix, and is therefore of full rank. Therefore, this is actually a so called type 1 break, and equivalent pseudo factor representation with double the number of factors.

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

### Factor Space Consistency

### Information Criteria (no. of factors) consistency



## Chen et al (CDG) (2014)

CDG propose a test statistic for the constancy factor loadings. Heuristically, their test statistic is based on the fact that under the null hypothesis that the factor loadings are constant, then the factors themselves (as estimated by PCA) should be orthogonal to one another across all time points. 

Hence, they show for a regression of one pseudo factor on the remaining (taken to be the first factor for simplicity, without loss of generality):
$$
f_{1, t} = \beta_0 + \beta_1 f_{2, t} + \beta_3 f_{3, t} + \dots + e_t
$$
testing for the stability of the regression coefficients (such as via a Bai and Perron procedure) is a therefore equivalent to testing for the constancy of factor loadings over time.

As one of the earlier works in the literature, their simulation design is also primitive, and for full understanding it shall be presented and re-cast into newer subsequent frameworks.

Note that due to using more traditional regression based supremum type tests, the test stat maximiser yields a natural estiamtor for the break fraction.

Of very important note is that CDG only consider the case of "augmented" breaks in the form of mean shifts in the loadings matrix - corresponding to a 

\newpage

## Corradi and Swanson (2014)

Corradi and Swanson (CS) propose, to date, the only methodology which is focused on the the effects of factor loading instability in the specific context of factor augmnented forecasting.  

Interestingly, their paper does not include a simulation exercise at all to investigate and confirm the power of their proposed test statistic. As such, this section is empty. Refer to the general literature review document for an overview/summary of their paper.

Without loss of generality, they focus on the usual $h$ step ahead forecast for some variable $y$ to be forecast, augmented with the use of estimated factors from some large dataset $X$. The factors are setup in the usual way as most DFMs:
$$
X_t = \mu_0 + \Lambda_{0, t} F_{0, t} + u_t,
$$
where $X_t$ is a $N \times 1$, $\Lambda_{0, t}$ is $N \times r$, $\mu_0$ is $N \times r$, $F_{0, t}$ is $r \times 1$, and $u_t$ is a $N \times 1$ error term.

The forecasting equation is defined as follows:
$$
\begin{aligned}
y_{t_h} 
&= \alpha_0 + \beta_{0, 1, t} F_{0, 1, t} + \dots + \beta_{0, r, t} F_{0, r, t} + \epsilon_{t + h}\\
&= \alpha_0 F_{0, t}' \beta_{0, t} + \epsilon_{t + h},
\end{aligned}
$$
which can also be augmented with any other forecasting regressors, such as lags of $y$ and lagged factors are needed. Note that in this general setup the loadings and regression coefficients are both allowed to time vary.

CS focus on two sources of instability: those from the factor loading matrices, and those from the regression coefficient, and subsequently define their null hypothesis as:
$$
H_0: \Lambda_{0, t} = \Lambda_0 \quad \text{and} \quad \beta_{0, t} = \beta_0 \; \forall \; t,
$$
versus the alternative that either one of the above conditions does not hold. Note that factor loadings are allowed to break in either the $N$ dimension (where only a certain fraction of series have their loadings break), or the $r$ dimensions (where a certain number of factors in general break), or both.

Their test statistic is based on the the covariance between the pseudo factors and the forecast target variable, and testing if a full sample version of this is different from that estimated via a rolling window approach. Heuristically, this is similar in spirit to a Hausman type statistic: under the null of structural stability, both the full sample and rolling window estimates converge to the same probability limit, but diverge under the alternative hypothesis of instability.

The proposed test statistic is shown to be asymptotically multivariate normally distributed, and its L2 norm after appropriately scaled is asymptotically chi squared distributed.

\newpage

## Han and Inoue (2014)

HI pioneered the basis of the dynamic factor model with structural breaks in the loading matrices, subsequently used as the basis by further state of the art contributions. 

Notably however, their work was published in Econometric Theory, and did not contain *any* empirical applications.

Although this representation was regarded as very advanced for its time, it is still annoyingly rather ambiguous and hard to work with. 

A glaring limitation of this framework is that it only considers breaks which affect *all* series. Indeed, the case where only some series undergo a break is mostly covered under type 1 break, however, a type 1 break can only be detected (or be considered to be a type 1 break at all) is the change in mean shifts is so large that the columns of the loading loading matrices are completely linearly independent. Note that the case of a type 2 break cannot allow for this - $\Lambda_2 = \Lambda_1 Z_0$ requires $Z_0$ to be a $r \times r$ square matrix, and hence rotate the loadings for *every* series along the $N$ dimension.

\newpage

## Baltagi et al (2017)

Baltagi's design roughly follows that of Bates et al (2013). The data is generates as follows:

$$
X_{it} = 
\begin{cases}
f_{0, t}' \lambda_{0, i} + f_{1, t}' \lambda_{1, i} + \sqrt{\theta_1}e_{it}, \quad \text{for regime 1} \\
f_{0, t}' \lambda_{0, i} + f_{1, t}' \lambda_{2, i} + \sqrt{\theta_2}e_{it}.
\end{cases}
$$ 
The number of pre break and post break factors are $r_1, r_2$ respectively, $r = max(r_1, r_2)$. Note that $r$ here does NOT denote the number of pseudo factors in an equivalent representation.

Any factors which disappear are allowed for as a loading becoming 0 in that regime. The parameters $\theta_1, \theta_2$ control the magnitude of the noise, and in this setup the authors opt to set $\theta_1 = r_1, \theta_2 = r_2$.

The factors are as generated as follows: 
$$
f_{t, p} = \rho f_{t - 1, p} + u_{t, p}, \quad \text{for} \quad t = 2, \dots, T, p = 1, \dots, r
$$ 
where $u_{t, p} \sim i.i.d. N(0, 1)$, and $f_{1, p} \sim N(0, 1/(1 - \rho^2))$ so that the factors have stationary distributions. The parameter $\rho$ is the AR(1) coefficient capturing serial correlation in the factors.

The error terms are generated as follows:
$$
e_{i, t} = \alpha e_{i, t-1} + v_{it},
$$ 
where the series $u_{t, p}$ and $v_{t, p}$ are mutually independent, and $v_t \sim N(0, \Omega)$, and $e_{(., 1)}$ is initialized at the stationary distribution $N(0, (\Omega)/(1 - \alpha^2))$. The scalar $\alpha$ captures the degree of serial correlation in errors, and $\Omega_{ij} = |\beta^{i - j}|$ captures the degree of cross sectional correlation within the errors.

Baltagi et al consider 3 different ways of generating factor loadings.

### Setup 1

The first setup allows for a change in the number of factors, and a partial change in the factor loadings, with $(r_1, r_2) = (3, 5)$ and one factor having stable loadings. The stable factor has its loading $\lambda_{0, i} ~ N(0, x_iR^2_i)$. The remaining factor loadings are both four dimensional, with the first two elements of $\lambda_{1, i} \sim N(0, x_i, R^2_i I_2)$ and its last two elements set to 0 (to yield 3 true factors in total), and $\lambda_{1, i} \sim N(0, x_i, R^2_i I_4)$. Hence, the number of pseudo factors in this setup is $r_1 + r_2 - 1 = 7$. The scalar $x_i R^2_i$ is determined such that the regression $R^2$ of series $i$ is equal to $R^2_i$.

### Setup 2

The second setup only allows for a change in the number of factors. Similarly, $(r_1, r_2) = (3, 5)$. Here, the first 3 factors all have stable loadings, and the first three elemnts of $\lambda_{0, i} ~ N(0, x_iR^2_i I_3)$. Both $\lambda_{1, i}, \lambda_{2, i}$ are two dimensional vectors, with $\lambda_{1, i}$ being set to 0, and $\lambda_{2, i} ~ N(0, x_iR^2_i I_2)$. Hence, the number of pseudo factors is $r_1 + r_2 - 3 = 5$.

### Setup 3

The third setup allows for only a partial change in the factor loadings, with $(r_1, r_2) = (3, 3)$, and one factor having stable loadings. In this case, $\lambda_{0, i} ~ N(0, x_iR^2_i I_1)$, $\lambda_{1, i} ~ N(0, x_iR^2_i I_2)$, and $\lambda_{2, i} = (1 - a)\lambda_{1, i} + \sqrt{2a - a^2 d_i}$, where $a \in [0, 1]$, and $d_i ~ N(0, x_iR^2_i I_2)$. The number of pseudo factors in general, is thus $3 + 3 - 1 = 5$, except in the case of $a = 0$. Thus, $a$ here captures the magnitude of factor loading changes, with the ratio of mean squared changes being equal to $\frac{4a}{3}$, and $a = 0.2, 0.6, 1$ are considered.

### Common setup notes

For all setups, the homogeneous case of $(\rho, \alpha, \beta) = (0, 0, 0)$ is considered (no serial correlation in factors, no serial correlation in errors, and no cross sectional correlation in errors respectively), and the more emprically relevant case of $(\rho, \alpha, \beta) = (0.5, 0.2, 0.2)$. For the homogeneous case, $R^2_i = 0.5$ is considered, and for the hetergenous case, $R^2_i ~ U(0.2, 0.8)$. Sample size of $T = 100, 20, 400$ and $N = 100, 200$ are considered. The break fraction is set to $\tau_0 = 0.25, 0.5$.

\newpage

## Baltagi et al (2021)

An extension to their existing paper which develops the inferential theory for subsequent testing of breaks in factor loadings. Their Monte Carlo design, thus remains mostly identical, but now generalised for the case of multiple breaks.

They consider a total of three factors, each independently generated according to an AR(3):

$$
f_{t, p} = \rho f_{t-1, p} + u_{t, p}, \quad u_{t} = (u_{t, 1}, u_{t, 2}, u_{t, 3})' \sim i.i.d. N(0, I_3),
$$ 
and $f_1 = (f_{1, 1}, f_{1, 2}, f_{1, 3})' \sim N(0, I_3/(1 - \rho^2)$ so that the factors are initialized at the stationary distribution.

The error terms are generated the same way as Baltagi et al 2017: 
$$
e_{i, t} = \alpha e_{i, t-1} + v_{it},
$$ 
where the series $u_{t, p}$ and $v_{t, p}$ are mutually independent, and $v_t \sim N(0, \Omega)$, and $e_{(., 1)}$ is initialized at the stationary distribution $N(0, (\Omega)/(1 - \alpha^2))$. The scalar $\alpha$ captures the degree of serial correlation in errors, and $\Omega_{ij} = |\beta^{i - j}|$ captures the degree of cross sectional correlation within the errors.

The loadings are generated in a much simpler way compared to Baltagi et al 2017, and differently according to each setup.

### Setup 1

Setup 1 contains no structural change, and is used as a null hypothesis case to help determine the size of the proposed test. The stable loadings are simply $\lambda_i \sim N(0, I_3/3)$ across $i$ and for all $t$.

### Setup 2

Setup 2 contains two structural changes, and hence three different regimes. The number of factors in each regime is $(2, 2, 3$ respectively, with $\lambda_{1, i} \sim N(0, I_2/2)$ and zeros in the last element, $\lambda_{2, i} \sim N(0, I_2/2)$ and zeroes in the last element, and $\lambda_{3, i} \sim N(0, I_3/3)$, with all factor loadings across all regimes being fully independent of one another. Because *all* loadings are changing completely in each regime, the number of pseudo factors is $2 + 2 + 3 = 7$.

### Setup 3

Setup 3 also contains two structural changes, and hence 3 regimes. It is similar to Setup 2, but has $(3, 3, 3)$ factors in each regime, $\lambda_{1, i} \sim N(0, I_3/3)$, $\lambda_{2, i} \sim N(0, I_3/3)$, $\lambda_{3, i} \sim N(0, I_3/3)$ and are all independent of one another. Similarly, because *all* loadings are changing completely for each regime, the number of pseudo factors is $3 + 3 + 3 = 9$.

### Common Setup Notes

All factors are independent of the loadings and errors, as usual. The change fractions are set to be $(0.3, 0.7)$.

The number of factors un each regime conditional on the estimated break date is done via Bai and Ng IC2, and ER and GR from Ahn and Horenstein.

Although theoretically the estimated break fraction is not consistent and only stochastically bounded of $O_p(1)$, the theoretical results show that the estimated factors in each regime conditional on even this inconsistent estimator is still robust, and this is supported by the simulation section.

### Other notes

Not exactly sure why, but Baltagi et al 2021 only consider the case where all loadings changing during a break - there are no stable loadings at all in any of their break setups (they do not consider the partial change case). What happens when there is a stable factor is unclear at this moment.

\newpage

## Ma and Su (2021)

Ma and Su propose an entirely new method motivated by the LASSO literature. As such, their method does not rely on the frameworks proposed by HI and Baltagi et al.

Work is needed to see if this can be converted and reconciled with the pre existing framework.

$$
X_{it} = \lambda_{it}' F_{t} + e_{it}
$$ 
where the factors are generated in a common way to all setups:
-   $F_t = (F_{1t}, F_{2t})'$ (2 x 1)
-   $F_{1t} = 0.6 F_{1, t - 1} + u_{1t}$, $u_{1t} \sim i.i.d. N(0, 1 - 0.6^2)$
-   $F_{1t} = 0.3 F_{2, t - 1} + u_{2t}$, $u_{2t} \sim i.i.d. N(0, 1 - 0.3^2)$.

The loadings and errors are generated separately for each setup.

### DGP1 (1 break)

$$
\lambda_{it} = 
\begin{cases}
\alpha_{i1} \quad t = 1, \dots t_1 - 1\\
\alpha_{i2} \quad t = t_1, \dots, T
\end{cases}
$$ 
where 
-    $\alpha_{i1} \sim i.i.d. N \left( (0.5b, 0.5b)', ((1, 0)', (0, 1)') \right)$, 
-    $\alpha_{i2} \sim i.i.d. N \left( (b, b)', ((1, 0)', (0, 1)') \right)$

### DGP2 (2 breaks)

$$
\lambda_{it} = 
\begin{cases}
\alpha_{i1} \quad t = 1, \dots t_1 - 1\\
\alpha_{i2} \quad t = t_1, \dots, t_2 - 1 \\
\alpha_{i3} \quad t = t_1, \dots, T
\end{cases}
$$ 
where 
-  $\alpha_{i1} \sim i.i.d. N \left( (0.5b, 0.5b)', ((1, 0)', (0, 1)') \right)$ 
-  $\alpha_{i2} \sim i.i.d. N \left( (b, b)', ((1, 0)', (0, 1)') \right)$ 
-  $\alpha_{i3} \sim i.i.d. N \left( (1.5b, 1.5b)', ((1, 0)', (0, 1)') \right)$

### DGP3 (no breaks, control)



## Bai, Han and Shi (2021, forthcoming)

## Su and Wang (2017)

Su and Wang similarly propose a new framework, and focus on the case for possibly time varying loadings. They model loadings as a smooth function of time and estimate them via local PCA regressions. Their main contribution is a test for time varying loadings based on the estimated squared common component.

Because the existing framework and literature has focused on one time breaks, there should be no easy way to re-concile this with the literature.

Also note that they have a VERY large simulation section, with 10+ (!) DGPs specified.

Hence, these are low priority.

## Su and Wang (2021)

Su and Wang modify their previous contribution in a follow up paper, and propose an easier to understand methodology based on the time varying loadings directly, rather the common components (which is harder to understand).

Similarly, this paper has a very large simulation section, but does seem to be be very similar to their previous paper.
