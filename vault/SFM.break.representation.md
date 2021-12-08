---
id: T4apcqDvjFydx29a2fyaN
title: Equivalent Representation Theorems
desc: ''
updated: 1638424040734
created: 1635165604337
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
\newcommand{\rank}[1]{\operatorname{rank} #1 }

An equivalent representation theorem in the context of dynamic factor models with breaks shows how a dynamic factor model with a structural break can equivalently (in the observational sense) be represents as a factor model without any breaks. 

Several attempts have been made at formalising this, and to date the most refined version being that of Baltagi et al.

Note that however, all of these theorems work on the premise of the break being in the loading. 

Note that in this section ONLY, $q$ DOES NOT refer to the number of dynamic factors - it instead refers to the number of factors which undergo a break. 

## Breitung and Eickmeier

Breitung and Eickmeier note that an SFM that exhibits breaks in their loadings can be equivalently represented as an SFM without breaks, but double the number of factors.

This is not entirely true (see later representation theorems), but the setup they consider is:

$$
y_{it} = f_t' \lambda_i^{(1)} + e_{it} \\
y_{it} = f_t' \lambda_i^{(2)} + e_{it}
$$

## CDG

[@chen_detecting_2014] propose a simply method for detecting big breaks in factor loadings.

This method was developed ONLY for breaks in factor loadings, even though breaks in loadings vs factors themselves cannot be separately identified.

They postulate that such a differentiation technique could be based on the estimated rank of the loading matrices in each subsample - essentially pointing towards the break classification system later proposed by [@han_tests_2015].

[@chen_detecting_2014] have a primitive version of an equivalent representation theorem, and a proof of an implication of the BNIC is provided in their appendix.

## Han and Inoue

[@han_tests_2015]'s first attempt at a representation theorem.

Let us consider the singular break case:

$$
X_{it} = \begin{cases}
F_{0, t}' \lambda_{0, i} + F_{1, t}' \lambda_{1, i} + e_{it}\ \quad \text{for} \quad t = 1, \dots, \floor{\tau T} \\
F_{0, t}' \lambda_{0, i} + F_{1, t}' \lambda_{2, i} + e_{it}\ \quad \text{for} \quad t = \floor{\tau T} + 1, \dots, T,
\end{cases}
$$
where $F_{0, t}$ is a $(r - q) \times 1$ vector of time invariant factors, $F_{1, t}$ is a $q \times 1$ dimensional factor whose loadings undergo structural change.

The matrix representation of the the previous setup is:

$$
\begin{aligned}
X &= 
\begin{bmatrix}
F^{0, 1} \Lambda_0' + F^{1, 1} \Lambda_1' \\
F^{0, 2} \Lambda_0' + F^{1, 2} \Lambda_1'
\end{bmatrix} + e \\
&= \begin{bmatrix}
F^{0, 1} & F^{1, 1} & 0 \\
F^{0, 2} & 0 & F^{1, 2}
\end{bmatrix} 
\begin{bmatrix} \Lambda_0 & \Lambda_1 & \Lambda_2 \end{bmatrix}' + e \\
&= \mathcal{F} \Theta + e.
\end{aligned}
$$

Note that the number of factors above is possible larger than $r$, and depends on the rank of $\Theta$. In general, $r \leq \rank{\Theta} \leq r = q$ and $\rank{\Theta}$. [@han_tests_2015] further classify breaks into 3 different types:

1. $rank(\Theta) = r$, Type 1 Break

The changes in $\lambda_{1, i} - \lambda_{2, i}$ need to be so idiosyncratic across $i$ such that $\Lambda_1$ and $\Lambda_2$ are linearly independent.

An attempt to interpret this is as follows.

The change in teh factor structure ultimately reflects a change in cross-correlations between variables related to common factors, that is, the loadings must change, given a set of estimated factors, to accurately capture (or represent) the change.

2. $r \lt rank(\Theta) \lt r + q$, Type 2 Break

The column rank of $[\Lambda_1 : \Lambda_2]$ is $q$, so that there exists a $q \times q$ matrix $Z_0$ such that $\Lambda_2 = \Lambda_1 Z_0$. 

A type 2 break implies that the "break" is simply a rotation or scaling of the existing loadings.

Note that $Z_0$ is allowed to be singular, in which case there will be emerging(disappearing) factors after the break. 

This singular transformation case is the most topical for practical applications, as people tend to be interested in emerging factors.

The practical interpretation of this is that the change in the factor strcuture ultimately reflects a change in the voltatility related to common factors, but with stable cross-correlations between variables related to common factors, such that a the loadings themselves are stable, given a set of estimated factors. Still, this is hard to interpret.

3. $rank(\Theta) = q$, Type 3 Break

This is a combination of Type 1 and Type 2 break.

What this precisely means heuristically is unknown, and this seems to be just a technical existence sort of thing. 

## Baltagi et al

### Singular Break

This was proposed by [@baltagi_identification_2017] as an extension to Han and Inoue's work.

Suppose that $\rank(\Theta) = r + q_1$, with $0 \leq q_1 \leq q$ and $[\Lambda_0 : \Lambda_1]$ is of full rank. Partition $[\Lambda_2]$ as $\Lambda_2 = [\Lambda_{21} : \Lambda_{22}]$, where $\Lambda_{21}$ is $N \times q_1$ and is linearly independent from $[\Lambda_0 : \Lambda_1]$, and $\Lambda_22$ are linear combinations of $[\Lambda_0 : \Lambda_1 : \Lambda_{21}]$. 

1. Type 1: $q_1 = q$

2. Type 2: $q_1 = 0$

3. Type 3: $0 < q_1 < q$

Assuming that $\Lambda_22 = [\Lambda_0 : \Lambda_1 : \Lambda_21]Z_1$ for some $(r + q_1) \times q_2$ matrix $Z_1$.

The model can then be re-written as follows

$$
[\Lambda_0 : \Lambda_1] = [\Lambda_0 : \Lambda_1 : \Lambda_{21}]A \\
[\Lambda_0 : \Lambda_2] = [\Lambda_0 : \Lambda_1 : \Lambda_{21}]B
$$
where

$$
A = \begin{bmatrix}
I_r \\
0_{q_1 \times r}
\end{bmatrix}, 
B = \begin{bmatrix}
I_{r - q} & 0_{(r - q) \times q_1} & \\
0_{q \times (r - q)} & 0_{q \times q_1} & : Z_1 \\
0_{(r - q) \times q_1} & I_{q_1} & 
\end{bmatrix}.
$$

Thus, the entire model can be re-written as

$$
\begin{aligned}
X &= 
\begin{bmatrix} 
\begin{bmatrix}
F^{0, 1} & F^{1, 1}
\end{bmatrix}
\begin{bmatrix}
\Lambda_0 & \Lambda_1
\end{bmatrix}' \\
\begin{bmatrix}
F^{0, 2} & F^{1, 2}
\end{bmatrix}
\begin{bmatrix}
\Lambda_0 & \Lambda_2
\end{bmatrix}'
\end{bmatrix} + e \\
&= \begin{bmatrix} 
\begin{bmatrix}
F^{0, 1} & F^{1, 1}
\end{bmatrix}
A' \\
\begin{bmatrix}
F^{0, 2} & F^{1, 2}
\end{bmatrix}
B'
\end{bmatrix}
\begin{bmatrix}
\Lambda_0 & \Lambda_1 & \Lambda_{21}
\end{bmatrix}' + e
\end{aligned}
$$

The above representation is useful, as it is clear that the PCA estimator will actually estimate a transformed version fo the factors. These transformed factors will undergo a break at time $\floor{\tau T}$, and this could lead to deterioation of forecast accuracy. 

How precisely this affect forecast performance however, is unclear.

The above representation theorem states clearly how many factor will be determined by any consistent estimator of $r$. The literature has actually stopped short of stating this definitively, presumably because the representation theorems do not cover all possible types of breaks. 

### Multiple Breaks

[@baltagi_estimating_2021]'s extension of their previous framework to the general case of multiple breaks.

## Notes

Changes in the variance of the dynamic factor idiosyncratic shocks seems to be something reasonable, but too difficult to cater for in practice.

This is because everything is based off of [@bai_determining_2002] assumptions, which require that the factors themselves have a constant second moment. 

The latter point is of interest, but I'm unclear how this may be achieved - ask supervisors.

