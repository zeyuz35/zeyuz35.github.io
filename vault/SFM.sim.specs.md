---
id: mC4GglXOGYJJAMdwMCE4j
title: Simulation Specification Quick Notes
desc: ''
updated: 1638337948210
created: 1638337553044
---

## Useful results

Some useful results when playing around with Monte Carlo Simulations.

It is thought that the following tend to be empirically relevant:

$$
AR(0.5) \\
AR(1.2, -0.5)
$$

## AR Results

AR1

Unconditional Mean: 
$$\frac{\beta_0}{1 - \beta_1}$$

Unconditional Variance: 
$$ 
\frac{\sigma^2}{1 - \beta_1^2}
$$

AR2

Unconditional Mean: 
$$
\frac{\beta_0}{1 - \beta_1 - \beta_2}
$$

Unconditonal Variance: 
$$\frac{(1 - \beta_2)\sigma^2}{(1 + \beta_2)(1 - \beta_1 - \beta_2)(1 + \beta_1 - \beta_2)}
$$ 