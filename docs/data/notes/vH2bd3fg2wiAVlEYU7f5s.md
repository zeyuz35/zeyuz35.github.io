
Introduction Section.


## Static Factor Models
Static Factor Models are denoted as 

$$
X_{it} = \lambda_{i}' F_t + e_{it}
$$
where $\lambda_{i}$ is $(r \times 1)$, $F_t = (F_{1t}, F_{2t}, \dots F_{r_t})'$ is $(r \times 1)$.

Or, equivalently:

$$
X_t = \Lambda F_t + e_t
$$
where $X_{t}$ is $(N \times r)$, $\Lambda = (\lambda_1', \lambda_2', \dots, \lambda_N')'$ is $(N \times r)$.

Or, equivalently:

$$
X = \Lambda' F + e
$$
where $X$ is $(T \times N)$, $\Lambda$ is $(N \times r)$, $F = (F_1, F_2, \dots, F_r)$ is $(r \times T)$.

## Dynamic Factor Models

Dynamic Factor Models are denoted as:

$$
X_t = \Lambda^*(L)f_t + e_t
$$
where the primitive shocks or factors $f_t$ is $(q \times 1)$, and the dynamics of $f_t$ are now explicitly clear via the use of the lag polynomial operator. The loading matrix $\Lambda^*$ is now $(N \times q)$Note that any dynamic factor model can be equivalently written in static form by treating the lags of factors as their own static factors.

The loading matrices $\Lambda$ or $\Lambda^*$ are called loadings, or filters in the dynamic case.

The dynamic factor model is much harder to estimate, but for most purposes can be estimated via the equivalent representation of a static model.

## Assumptions

In both static and dynamic factors models the common component is assumed to be uncorrelated with the idiosyncratic error across all time and cross sectional units.

The error term itself has looser restrictions and assumptions. If $e_{it}$ is assumed to be spherical (no cross sectional correlation OR serial correlation), then we have a so called exact factor model.

This is quite unrealistic, and typically $e_{it}$ is allowed to have some mild cross sectional correlation, and this leads to a so called approximate factor model.

If $e_{it}$ is additionally allowed to have serial correlation, then we have a generalised factor model. 

The latter two cases are more realistic, but can only be asymptotically estimated when there is large $N$ in addition to the usual large $T$, therefore leading to the necessary "double asymptotics in the literature".

## Representation in AR/MA 

There is a large section here using representation using AR/MA forms, but I'm not sure it is entirely relevant.

