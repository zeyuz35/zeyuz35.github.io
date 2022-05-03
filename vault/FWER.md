---
id: ce4n0eeatts2pl5w3623mr9
title: Family Wise Error Rates
desc: ''
updated: 1651558633146
created: 1651556089174
---

Overview of Family Wise Error Rates, because I need to look into for this the two different
test procedures

This literature is called the FWER literature, and here lists some notable contributions.

A "family" is 

- any collection of inference for which it is meanginful to take into account some combined 
measure of error
- potential selective inference that is being faced: a family is the smallest set of items 
in an analysis, interchangeable about their meaning for the goal of research, from which
selection of results for action, presentation or highlighting could be made

Basically, the definition is very loose, and not something to get caught up on

## Plan

There are many different ways to control the FWER, and I think this is a distinct enough 
step to to allow for customization

Our specific case is rather simple, only two hypotheses, however, the correlation of the two
test statistics is in general going to be unknown

They are two completely different tests, so this does rule out some procedures

Anyway, a solid enough plan for now is to return the test statistics and relevant sampling
distributions, so that we can pick and choose which method we want for now

## Bonferroni Correction

The most straightforward one - simply adjust alpha to be alpha/p, where p is the no. of tests

Alternatively, one could "weight" the p values in any way, as long as they sum up to 
the desired overall significance level

The Bonferroni correction is known to be very conservative if there are a large no. of tests
and/or the test statistics are positively correlated

I.e. the probabilities of producing false negatives is higher

No consensus on how to define a family in general (see above), and the results are different
depending on what tests are put into the family

It is however, exceedingly simple to implement

## Holm/ Holm-Bonferroni stepdown procedure

A slightly more involved method, but still similar to Bonferroni tests

Order the p values from lowest to highest

In total there are m tests

Is P1 < alpha/M? If sor, proceed, otherwise, DO NOT REJECT

Is P2 < alpha/(m - 1)? If so, proceed, otherwise DO NOT REJECT

Continue

Intuition

k denotes the first p value that is too high to be rejected

If k = 1, then there are no null hypotheses which can be rejected

If k is not defined (all rejected), then all p values were sufficiently low enough, and 
therefore all null hypotheses are rejected (none are accepted)

Example

H1, H2, H3, H4

H4 could be rejected, H1 could be rejected, but H2 is NOT rejected

Because the procedure STOPS at the first non rejection, H3 is ALSO not rejected

This procedure does not require any assumptions (at least that I can tell)

There are other methods, but there are more restrictive

### Implementing Bonferroni and Holm

The above two are actually both easy to implement

Notice that for Bonferroni:

Rejection if P < alpma/m

Therefore, this is the same as reject if P*m < alpha

So, just multiply all p values by m

Notice that for Holm

Reject if P < alpha/(m - k + 1)

This is the same as reject if P *(m -k + 1) < alpha

Therefore, multiply each P value by their reverse index

## Sidak or Dunn-Sidak

This correction is *exact* for tests that are completely independent, conservative for tests
that are positively correlated, and liberal (?) for tests that are negatively correlated

Given m different hypotheses, and a family wise error rate of alpha, 

set the individual significance values as 1 - (1 - alpha)^(1/m)

## Hochberg stepup procedure

Order the p values from lowest to highest

Let R be the largest k, such that Pk < alpha/(m - k + 1)

However, this procedure only holds under non-negative correlation bewteen the test statistics

## Romano and Wolf (paper provided)

I believe this is one of the most up to date developments in the literature

I don't think this is applicable to my thesis, it is much more concerned with say, testing
many different returns against a benchmark



