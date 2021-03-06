---
id: tpEdCD47bDkWqJCrnZxOq
title: General Advice
desc: ''
updated: 1647404872053
created: 1637722333592
---

## General


## Writing Tips

John H. Cochrane is very opinionated, but provides some solid advice:

https://static1.squarespace.com/static/5e6033a4ea02d801f37e15bb/t/5eea8ee7c4488718b640f3c6/1592430312374/phd_paper_writing.pdf

As usual, make sure to tailor the advice to your own needs. John Cochrane presumably doesn't follow his own advice.

Additionally, although John is a fellow of the Econometric Society, he is more of an empirical finance/macroeconomics person, and as such his advice is more tailored towards empirical papers. 
## Frequentist Advice

1. Come up with an empirical motivation - for theory, this does not have to be too strong
2. OR come up with an idea for a new test statistics/estimator
3. Derive its distribution under the null, typically this will be Normal, Chi squared, etc
4. Derive its *behaviour* under the alternative hypothesis, and make sure this actually diverges from the null distribution
5. Do a simulation study to confirm that the finite sample performance is OK, at least theoretically
6. Provide some empirical application

## Bayesian Advice

*crickets*

## Applied Advice

1. Come up with an empirical motivation. For applied work, this needs to be stronger, and something that's "easy" is to do something motivated by current affairs
  - Bonsoo and Ben say that COVID in particular are very topical, and because no one really knows what they are doing wrt COVID, anything will likely be very popular
2. Try to apply some existing model, either directly, or with some slight adjustments
3. Empirical work may be easier in this regard, because a completely new proposal may not be necessary, novel use of existing methods itself is novel
4. Try to get some interesting results, but also not too interesting such that they completely contradict the literature
5. Make sure results are robust to some degree, you will need to run numerous robustness checks


# Chapter 1 Comments

Bin and Bonsoo say that the notation for ERT needs to be clearer (hard to do this for presentation)

Bin was a little confused about how the cross product of loadings would tease out the factor variance

Bin said to ignore earlier comments

## Bin

Personalyl much prefers Latent Factor Model formulation which uses Random Matrix Theory, but IMO this is completely different

Also prefers use of Ahn and Horenstein Estimator, because apparently this has a numerator/denominator mechanism to already control for factor variance? Need to look into this. Even so, should not be an issue because changes in factor variance do not affect PCA assumptions

ERT notation is confusing, needs to be made better somehow...

Partial breaks would be interesting, but obviously beyond the scope of the paper

## Natalia

Issue of potentially weak factors and loadings (this is showing up in simulations already)

Robustness with regards to weak factors/loadings

Entire analysis hinges on accurate estimation of break fraction, as well as no. of factors

Natalia is of the belief that small breaks may be more empirically prevalent, relevant and interesting. This may necessitate the use of additional regularity assumptions to ensure that breaks are "large" - also something that seems to be creeping up on simulation study right now
