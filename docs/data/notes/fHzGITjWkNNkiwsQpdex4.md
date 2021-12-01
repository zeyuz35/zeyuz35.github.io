
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
X_t = \Lambda_t F_t + e_t \\
X = F \Lambda' + \mathbf{e}.
$$
which correspond to the individual, time slice, and whole panel representations respectively. 

This is an equivalent representation of the true, dynamic form:

$$
X_{it} = \lambda_i (L)'f_t + \epsilon_{it}
$$

where $f_t$ is a $q$ dimensional vector of dynamic factors, also known as primitive shocks, and $\lambda_i(L)'$ denotes the $q$ dimensional lag polynomial, also called the "dynamic factor loadings".

With the above, breaks can occur in the following ways:

1. Breaks in the intercept of $x_{it}$ (mean shift)
2. Breaks in the loadings $\lambda_{it}$
3. Breaks in the idiosyncratic errors $e_{it}$
4. Breaks in the true dynamic factors:
    - Breaks in the dynamics of the factors
    - Breaks in the idiosyncratic shocks $\epsilon$

It can be shown that a break in the intercept can be equivalent to a break in the loading (set one factor to be constant).

Currently, representation theorems handle the cases of breaks in factor loadings quite comprehensively.

Breaks in idiosyncratic errors, assuming that the errors are still independent of the factors and loadings, do not affect estimation, except for the general case of changing the signal to noise ratio.

Breaks in the intercept of the series can be easily viewed as breaks in the loadings (an intercept is really just a constant factor).


#### Gap: Break in Factor Dynamics

However, a notable gap is what happens when there is a break in the factor dynamics. This is because all of the theory developed thus far has been working within the static factor model framework.

This is extra complicated because a break in the loadings cannot be distinguished from a break in the factors.

All of the literature explicitly have the same assumptions (or some slight variation) as [@bai_determining_2002] and [@bai_inferential_2003], which crucially have:

$$
E||F_t^0|| < \infty \\
\frac{1}{T} \sumT F_t^0 F_t^{0 \prime} \convp \Sigma_{F, (r \times r)} \geq 0
$$

Even all papers which are designed to test for structural breaks actually assume that the factor process is stationary across all regimes.

A break in factor dynamics is something I think is empirically relevant:

  - the dynamic factors can be interpreted as the primitive shocks which propagate through the economy, in the context of factor models
  - Even if one is not inclined to believe in a change in dynamics of the factors, it could be more easily argued that a change in the variance of the idiosyncratic shocks to the factors is believable

#### How to model breaks in dynamics?

Literature linking the dynamic factors and the static factors tends to be scarce.

[@bai_determining_2007] is the best resource on this - they propose an IC for $q$, the number of dynamic factors. Crucially, they also prove that any dynamic factors in a DFM have an equivalent static factor model representation.

However, the actual no. of factors can be ambiguous depending on the what the dynamics precisely are, and I'm less comfortable with this.

### Small Simulation Set up

Simulation set up: factor process changes from AR1 to AR2 (made sure it was stationary this time!).

Conjecture: if one can find a way to find the break, then conditional on partitioning the break, the number of factors in each should be consistent.

However, this leads to the problem of testing for such a break.

Simulation shows that existing tests are mixed against this. [@han_tests_2015] has some power, but [@baltagi_identification_2017] does not.

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


However, interestingly, 

Keep in mind that the economics literature tends to identify at most 4 primitive shocks, theoretically and empirically via estimation methods. 