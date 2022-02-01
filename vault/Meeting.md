---
id: fHzGITjWkNNkiwsQpdex4
title: Meeting
desc: ''
updated: 1642598168190
created: 1634221843124
bibliography: [references.bib]
reference-section-title: References
---

\newcommand{\sumT}{\sum_{t = 1}^{T}}
\newcommand{\sumTs}{\sum_{s = 1}^{T}}
\newcommand{\sumN}{\sum_{i = 1}^{N}}
\newcommand{\sumNj}{\sum_{j = 1}^{N}}
\newcommand{\convp}{\overset{p}{\to}}
\newcommand{\convd}{\overset{d}{\to}}
\newcommand{\limN}{\lim_{N \to \infty}}
\newcommand{\limT}{\lim_{T \to \infty}}
\newcommand{\plimT}{\operatorname{plim}_{T \to \infty}}
\newcommand{\plimN}{\operatorname{plim}_{N \to \infty}}
\newcommand{\plimNT}{\operatorname{plim}_{N,T \to \infty}}
\newcommand{\ceil}[1]{\left \lceil #1 \right \rceil }
\newcommand{\floor}[1]{\left \lfloor #1 \right \rfloor }
\newcommand{\sumTfloor}{\sum_{t = 1}^{\floor{\tau T}}}
\newcommand{\sumTfloort}{\sum_{t = \floor{\tau T + 1}}^{T}}

# Meeting Notes

Latest agenda

Go through what has been done, in a very rudimentary presentation

Mainly focus on the empirical result, this was quickest to put together

Ask about steps in helping to prove consistency results (skeleton of proof)

Monte Carlo questions

Simulate factors and loadings, and hold them fixed across replications?

## Focus Question

How many static factors are estimated by various information criteria in the presence of structural breaks? 

### Answer:

The number of factors of as estimated by any consistent estimator is consistent for an equivalent representation of the model, with constant loadings. Such an equivalent representation needs to be given by an equivalent representation theorem, see [@han_tests_2015] or [@baltagi_identification_2017], [@baltagi_estimating_2021]. These are the only representation theorems known to exist so far.

Note that a direct implication of these theorems is that the number of pseudo factors (static factors) for this representation can only increase as the result of breaks.

How many extra factors, if any, are estimated depends on the type of break in the loadings. 

It is important to note that standard estimators for the number of static factors are consistent for the number of pseudo factors. [@han_tests_2015] and [@baltagi_identification_2017] both have this as propositions, but strangely do not emphasize this. Other authors which were published before these frameworks have also proved similar results, but for more restrictive types of breaks (e.g. [@chen_detecting_2014]. Presumably, this is because representation theorems are not comprehensive enough yet to cover *all* possible types of structural breaks.

### Sources of possible breaks

Let us recall that a dynamic factor model can be written in the following static form:

$$
X_{it} = \lambda_{it}' F_t + e_{it} \\
X_t = \Lambda F_t + e_t \\
X = F \Lambda' + \mathbf{e}.
$$
which correspond to the individual, time slice, and whole panel representations respectively. 

Alternatively, there exists a strand of literature which prefers to work with the original *dynamic* form of the dynamic factor model:

$$
x_{it} = \lambda_i'(L)f_t + e_{it}
$$

where $\lambda_i(L) = (1 - \lambda_{1i}L ) - \dots - \lambda_{is}(L)) f_t$ is a vector fo dynamic loadings of order $s$. Note that some authors distinguish a dynamic factor model to be models such that $s$ is finite from a *generalized* dynamic factor model where $s$ is allowed to be infinite. In either case, the vector of dynamic factors $f_t$ (also referred to as primitive shocks) is assumed to evolve according to:

$$
f_t = C(L) \epsilon_t
$$

where $\epsilon_t$ are assumed to be zero mean, i.i.d. factor innovations, and both $f_t$ and $\epsilon_t$ are $q$ dimensional. 

Putting the two together, we have:

$$
x_{it} = \lambda_i(L)' C(L) \epsilon_t + e_{it}
$$

corresponding to the notation used in [@bai_large_2008]'s review chapter. Note that [@stock_chapter_2016], [@forni_generalized_2000] each use somewhat different notation.

This in turn can be shown shown to have a direct mapping to the static factor model representation:

$$
X_t = \Lambda F_t + e_t
$$

where $F_t$ is interpreted to contain the leads and lags of $f_t$. More generally, the relationship that $r = q(s + 1)$ always holds. Confusingly, because $F_t$ in this representation may be singular, the number of static factors estimated by IC is $r^* \leq r$, because some static factors may be perfect linear combinations of leads and lags of $f_t$.

With the above, breaks can occur in the following ways:

1. Breaks in the intercept of $x_{it}$ (mean shift)
2. Breaks in the loadings $\lambda_{it}$
3. Breaks in the idiosyncratic errors $e_{it}$
4. Breaks in the true dynamic factor process:
    - Breaks in the dynamics of the factors, either in the autocorrelation, or the number of lags included
    - Breaks in the factor innovations  $\epsilon$

It can be shown that a break in the intercept can be equivalent to a break in the loading (set one factor to be constant).

Breaks in the intercept of the series can be easily viewed as breaks in the loadings (an intercept is really just a constant factor).

Currently, representation theorems handle the cases of breaks in factor loadings quite comprehensively. These were all formulated for the static factor representation, and *only* for the case of breaks in $\Lambda$.


#### Gap: Break in Factor Dynamics

However, a notable gap is what happens when there is a break in the factor dynamics. This is because all of the theory developed thus far has been working within the static factor model framework.

Crucially, due tot eh multiplicative relationship between the loadings and factors, it is not possible (at least to the best of our knowledge) to disentangle breaks in the loadings from breaks in the factors. All papers working within the static framework have required to following strengthened assumption:

$$
E(f_t f_t') = \Sigma_F \\
\frac{1}{k_0} \sum_{t = 1}^{k_0} f_t f_t' \convp \Sigma_F \\
\frac{1}{T - k_0} \sum_{t = k_0 + 1}^{T} f_t f_t' \convp \Sigma_F
$$

which explicitly assumes piecewise stationarity in the static factor space. This has been waved off as an identification condition (which it is), but has very profound practical impacts for the interpretation of these resulting tests. Namely, due to this identifying assumption, *all* breaks are absorbed as breaks in the loadings. Therefore, these tests are really testing for breaks in the loadings, intercept, factor dynamics and factor loadings all at once. [@stock_chapter_2016]'s conjecture that these tests have power against factor dynamics is correct, and work is needed to help disentangle this.

A break in factor dynamics is something I think is empirically relevant:

  - the dynamic factors can be interpreted as the primitive shocks which propagate through the economy, in the context of factor models
  - Even if one is not inclined to believe in a change in dynamics of the factors, it could be more easily argued that a change in the variance of the idiosyncratic shocks to the factors is believable

#### Issues

[@breitung_testing_2011]'s seminal paper on testing for structural breaks *can* be interpreted correctly as a break in loadings. Unfortunately, this is very simply and univariate, and does not generalise to multiple series because 1. the error terms are allowed to be cross sectionally and serially correlated, and 2. the cross sectional dimension is allowed to go to infinity, which results in further issues (e.g. inverting an infinitely large covariance matrix).

[@han_tests_2015] and [@baltagi_identification_2017] introduce the identification condition above, and artificially cast the issue of breaks in possible infinitely many series into the issue of breaks in finitely many factors. But this results in the identification issues.

Directly working with the original model is conceptually the most direct and preferred approach, if you can work around the infinite dimensions. [@ma_estimation_2018] are the only paper which do this via a shrinkage approach, but it is very complicated, and does not allow for a differing no. of factors.



#### How to model breaks in dynamics?

Literature linking the dynamic factors and the static factors tends to be scarce.

[@bai_determining_2007] is the best resource on this - they propose an IC for $q$, the number of dynamic factors. Crucially, they also prove that any dynamic factors in a DFM have an equivalent static factor model representation.

### Small Simulation Set up

Simulation set up: factor process changes from AR1 to AR2 (made sure it was stationary this time!).

Conjecture: if one can find a way to find the break, then conditional on partitioning the break, the number of factors in each should be consistent.

Simulation results confirm that these tests all have power against detecting these breaks in factor dynamics.

[@bai_determining_2007] provide a representation theorem for how a dynamic factor model can always be written as a static one. However, the actual no. of factors can be ambiguous depending on the what the dynamics precisely are.

### New Research Question

More precise research question:

- How does the no. of static and/or dynamic factors change when there is a break in the factor dynamics?
- Simulation results suggest that breaks in factor dynamics tend not to affect the no. of factors estimated 
- how does this reconcile/extend current representation theorems?

Question for supervisors

- Unclear with how precisely static factors map into dynamic factors (question for Ben)
- Do factors breaking actually sound reasonable?

Personal conjectures:

- a change in the loadings has a fundamentally different interpretation, this suggests the change is structural, in the sense that the loadings may have shifted etc
- a change in the loadings can be interpreted as the way that different series responds has changed, but the fundamental structural of the economy itself has not (though this itself is up for debate)
- however, a change in the factor dynamics itself suggests something even more fundamental has changed
- changes in variance are difficult to identify and map with changes in loadings themselves, this could be argued as a mis specification of sorts
- Example: more migration, affects supply shock directly
- new targeted policy, only affects loadings or how people respond to things
- vs a counterexample, such as COVID, which arguably has changed both

## Potential Ideas

Brainstorm here, not too sure...

Need a test that has power against this type of break:

    - propose a new one
    - adjust an existing one (show via some representation that a change in dynamics can be viewed as a change in loadings, think this is possible for some breaks)

Feasible generalized PCA (two step)

## Other unrelated ideas

Sizing the break, conditional on a consistent break date estimator

- this is not intuitive, need to do something like $||\Lambda_1 - \Lambda_0||$ as a measure of break size, and I'm not sure how well this can be interpreted anyway
- this is also unfeasible due to the infinite dimension of such a matrix
- Or, more ambitiously, come up with an estimation method which estimates the same set of factors, but allows the loadings to be different in each regime
- [@cheng_shrinkage_2016] in their last section provides the closest thing to a decomposition of breaks
- could try to apply this decomposition for various datasets and find something interesting as an empirical paper...



## Empirical Motivation

The number of factors does change on FREDMD. In general, the number of factors has been empirically observed to be increasing over time in various macroeconomic datasets.

US Data [@stock_forecasting_2021]

FREDMD [@mccracken_fred-md_nodate]

CANMD [@fortin-gagnon_large_nodate]

AUMD [@hartigan_factor_2020]

There does exist a UKMD as well, but I don't recall the authors having run PCA on this yet. Not surprised if similar behaviour happens.

There is a monte carlo study which shows that sometimes the number of static factors is not strictly increasing - this was done using expanding windows, and happened low enough times that I'm willing to chalk it up to consistency.

Keep in mind that the economics literature tends to identify at most 4 primitive shocks, theoretically and empirically via estimation methods. 

## Threshold Idea

Skeleton of what this paper would look like

Already confirmed that second moments process of pseudo factors is highly correlated with breaks in mid 1970s, late 1970s, early 2000s, and GFC. Finding a suitable threshold should be very easy to justify this.

If we are prepared to assume piece wise stationarity, and inability to separately identify factor loadings and factor dynamic changes, these we can use this directly with some multivariate threshold model. 

The last two points should be fairly straightforward.

The main draw of this paper will then be the development of some new representation theorem which shows that existence of some threshold mechanism will result in possibly more factors. This is much trickier, but just follow in the footsteps of [@han_tests_2015].

