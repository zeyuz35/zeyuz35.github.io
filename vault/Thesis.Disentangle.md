---
id: 3CJuINQspPvgBEeXkWbrU
title: Disentangle
desc: ''
updated: 1652675319774
created: 1643941577338
---

## Brief Review

PCA is consistent for time invariant loadings, and non stationary factors.

Stock and Watson originally developed forecasting theory which required stationary factors

But Bai and Ng later on loosened this theory to be consistent with the PCA assumptions

Therefore, from an applied perspective, time varying loadings are problematic as this augments the factor space, whereas time invariant factors are not, as they do not augment the factor space

Note that there is the special case of integrated factors/series, but this is a whole different literature

It should be interest to researchers applied or otherwise to sufficiently differentiate the *types* of breaks that have occurred

This is because:

1. the interpretation of the breaks in arguably different (Type 1 is shift in loadings), Type 2 is rotation in ALL loadings, or arguably more simply, a change in factor dynamics
2. their effects on PCA are different, Type 1 augments and leads to more factors, but Type 2 does not (usually)

Existing papers can tests for the existence of these breaks and estimate them, but to date nothing has been accomplished that can distinguish between them

The closest are CDG test, which has no power against special kinds of Type 2 breaks (and works based on this), and DBH estimator, which has different properties for different types

Initially, the idea was to try to adjust the dataset so that only a certain type of break remained, then tease out the type of break that way

But this framework was much too clunky, and I did not believe this was possible for Type 1 breaks, due to the setup

## Proposal

Now, we to propose two different tests:

Z test, testing whether Type 2 break exists and

W test, testing whether Type 1 breaks exists

The main empirical story (and there is some evidence for) is that the Great Moderation was just a rotational change, or change in factor variance, vs GFC, which is a change in loadings AND factor dynamics

Using the result of the two results, it is possible to tease out which type of break is present

This is working very well in simulations

HOWEVER, the main issue is that the null hypothesis may be too "strict"

in the sense that because Z and W are both rather large matrices, any slight violation of this is technically in the null hypothesis

This is manifesting itself in the empirical data rejecting both of these tests... 

Even though the story for the GM is that it is only a Type 2 break, and should only be rejecting on the Z test, and does exhibit a comparatively smaller W test statistic

Therefore, need to reformulate/loosen null hypothesis

An idea to do this is to get inspiration from the Bates paper, because there a looser conditions on the size of the break, in some sense anyway

## Testing

There are a few different options for us to take if we go for actual testing

We could try to come up with our own test, this will likely require formulating a test based on eigenvalues, which is not straightforward

OR, we could try to cast our test in the framework of say, a Hausman test...

Not sure how the Hausman test would work

OR, we could try to leverage an existing test, such as Han and Inoue or BKW

It seems that Tracy WIdom Distribution is used for distribution of eigenvalues...

## Empirical Results

The results are definitely not as robust as they could be. In general, a very low no. of factors helps with the narrative. However, even small changes/increase in the no. of factors can change the results

It is therefore very important to look at precisely *what* the factors are loading onto, and then judge whether this is in line with what the practitioner is really trying to do

### Great Moderation

Background:

Mainly interpreted and documented as a decrease in volatility in output and prices

Therefore, keep this in mind when running the test

The standard ON estimator selects something like 3, 5, 2 factors

This is usually sufficient to capture the main output and price variables, and the results from this are fairly robust

Empirically:

First Regime:

1. Output
2. ...
3. ...
4. ... Price

Second Regime:

1. Output
2. Price

The above looks quite strange, but it is fairly straightforward to show that this sort of "re-shuffling" has be represented as a Type 2a break

Therefore, for the purposes of disentanglement, minimal projection is actually necessary...

I think in retrospect this should be a main selling point of the paper, because it is not at all obvious that from a technical standpoint, out method can accurately accomodate for this

### Global Financial Crisis

First Regime:

1. Labour + Output
2. Price
3. Consumption

Second Regime:

1. Labour, Interest, Consumption
2. Consumption
3. Price

The above looks to be *at least* a Type 2a break

AHER suggests only 1 factor, i.e. only labour/output. If this is the main focus, then this is a Type 2 break only

ON suggests something similar to the above

BNIC suggests something like six factors, and this tends to include more effects of interest rates and stock prices. When these are included, there is too much noise, and the null can't be rejected at all

This suggests that the labour/output factor is a type 2 break, but the remaining two factors (Price and consumption) are perhaps at least Type 1 breaks. There is some rudimentary evidence for this, it does seem that not all series have changed in the same way.

