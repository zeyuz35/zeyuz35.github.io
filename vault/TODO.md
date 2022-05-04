---
id: BMClpTRP3V8ITqM7R4kh0
title: To Do List
desc: ''
updated: 1651211582142
created: 1635455071285
---

Broad TODO list of things to do - revisit and keep updated!

## DFM Package

The main backend of everything. 

Make this focused and very good at estimating factor models via PCA.

You will need to code up forecasting related functions later on - this will be the main sell of this program.

### Other Factor Models

LFM is done

GDFM is pending, this is a pain to understand and get working, but seems as if the theory 
is more tasteful, like LFM

## Empirical Chapter

Main empirical motivating chapter

This is not a main chapter per se, and it basically an expanded version of the work that is
presented as a motivating example

Several other people do PhDs in this areas all provide similar chapters as a Chapter 1

My contribution of this should be the comprehensive expansion of this to all datasets, 
not just FREDMD and an empirical discussion on how these instabilities are different, if
at all



## Disentangle Chapter

I think Bonsoo has gone straight ahead to position this as a paper focused on testing, as
opposed to estimation.

Skeleton of proof

Show that estimate of factor variance does indeed converge (should be easy, just apply BN)

Show that deflating by this in a projection gets rid of the break

Will need to do the above for both Type 1 and Type 2 breaks, because they are different

Not sure if Type 3 is needed, hopefully not (this would constitute another 2 proofs)

Show that the projected dataset from either procedure will behave correctly under the 
null hypothesis

NEVERMIND, Bonsoo was just a bit concerned that I didn't think the skeleton of this through

Anyways, the skeleton is still the same, and the main thing to do is to prove that the
adjustment procedures can legitimately remove their respective breaks.

However, before we do this, the simulation results look a little strange

I think this is because the Z matrix or whatever can sometime not result in a guaranteed
positive definite matrix (although it is always invertible)

Will need to brainstorm a way to get around this

And, also look into other matrix decompositions, because sometimes the eigendecomp 
doesn't actually converge...

Checked other papers' simulation setups

Han and Inoue only consider a scalar scaling for Type 2 breaks (essentially equal to diagonal Z)

Baltagi do not even focus on it

DBH provide the closest, and restrict C to be lower triangular (not sure why...)

I think it is not really possible to recover Z in a meaningful way

Instead, make it simpler (?) and just focus on a pseudo Generalised PCA procedure

Type 2 adjustment does indeed seem to work on simulations (and quite well, usually)

Even though on a basic statistical level it does not - this is due to the way that eigen transformations work, I think

The convergence property is close, but not exact, and I think this is because

eigen(XX') could be including effects of the noise as well, in finite sample

eigen(XX') include effects of the noise, but the noise is shrinking as T, N go to infinity, so this is usually not as issue

### Thinking of projection

Bonsoo suggested that makybe some sort of projection for Type 1 would be better

Type 1 Break is by definition an idiosyncratic break, i.e. there does not exist a translation

The issue is that after PCA, a semi translation may exist - but does this count as Type 3?

I think Type 3 is strictly when some factors undergo Type 1, and others Type 3

Because if a factor undergoes Type 1 and Type 3, this is technically just a Type 1, for that
one particular factor

Again, HI did not focus too much on defining/differentiating the different types of breaks

Idea

Projection should be consistent for Z up to a rotation

If there exists such a Z, then projection should find it "well" and the residuals should
be "small"

If not, then the residuals will be "large"

I.e. the residuals represent the bits that cannot be explained by the projection, if there
is any

Alternative Type 2 Adjustment idea:
Set Lambda2 = Lambda1 + the errors from this projection
I.e. Lambda1 without the projection/rotation, but with th errors added on

The errors represent any possible type 1 breaks...
We wish to get rid of any type 1 breaks, but preserve any Type 2 breaks

Therefore, set Lambda2 = Lambda2' Lambda1 (the projected version)

This method has some major issues, the convergence to a "good" Z is very poor, though
does improve with larger N

I'm fairly certain this is because PCA will estimate two arbitrary rotations

Idea: 
Change both sets of loadings to the same basis, by multiplying F1 Lambda2
Then use the changed basis version of Lambda 2...

The projection formulation is very good for characterizing Type 1 and Type 2 breaks

Working from this, it is easy to come with a test that only has power against Type 1 breaks

However, it is difficult to come up with a test statistic that only has power against Type 2
breaks, because this happens to have power against Type 0 breaks (no breaks) as well

This is because Type 2 breaks are currently characterized as there existing some Z that is not 0, 
which the identity matrix technically does qualify for

SCRATCH the ABOVE.

Recall that we are working with the assumption that THERE IS A BREAK already in the model.

Indeed, if there is no break, then Lambda_2 and Lambda_1 do not actually exist 
(they would be in Lambda_0) and so the exercise is not identified/strange anyway

Same idea to if you try to estimate a threshold model, when there is no threshold effect
(things behave very strangely because of a lack of identification issue)

So, Bonsoo and Ben both say that this is not an issue

TODO FOR NOW

Try to get a very vague idea of what the distribution looks like

and we can do this via a simple Bootstrap procedure (residual)

Deriving the distribution for each singular test should actually be farily straightforward

HOWEVER, the issue lies in the fact that the two tests need to be combined together
and they are very likely (almost certainly) correlated

Deriving a proper expression/theory for how to control the distribution/significance level properly
could be very difficult

So we need to consider a bootstrap. How to set up this bootstrap is itself difficult

but FOR NOW, just consider a standard residual bootstrap (this should be easy to implement)

Fit a DFM to the data, then bootstrap the residuals to generate more bootstrap realisations

Remember that the goal is to simulate the distribution UNDER THE NULL HYPOTHESIS

Use these empirical distributions very simply for now...

Question:
How exactly to convert Wtilde and Ztilde to a formal test statistic?

Should be easy, just consider the norm of them... or something similar...

Type sof Bootstrap:

i.i.d. Simple Residual Bootstrap

Cross sectional correlation  - WILD Bootstrap

Serial Correlation - Block Bootstrap

Cross sectional + serial - Block Wild Bootstrap

The simple residual bootstrap loses power if there is extra correlation in the residuals

Therefore, focus on simple bootstrap for now, and see if how the power is

If the power is very good anyway, then this is promising! THEN we can follow through and 
focus on more difficult bootstraps

boot package is the premier package for bootstraps, but it doesn't seem to implement the above...

Also, everything in the literature is focused on either cross sectional, or time series data
not really panel data

Code up some functions to bootstrap panel data specifically... (large N and T)



## Forecasting Chapter

Need to discuss with Ben further. However, as a good starting point, just start from
Stock and Watson forecasting equation, and see what happens

Ben is decidedly not too knowledgeable for PCA. 

Bai and Ng showed that under standard PCA assumptions, then estimated factors can be
treated as observable. Theoretically this says that Type 2 breaks are still OK.

If $f_t$ is observed and has a change in its variance, then this should not have any issue.

Ben thinks the use of estimated factors may introduce some issues.

Also, the main point now is that is it unclear how Type 1, Type 2 breaks etc could interfere
with a forecasting regression. 

Baltagi thinks that a type 2 break necessarily introduce a break in the intercept, but
this is due to their own interpretation of the break.

Refer to [[Thesis.forecasting]] for more details.

Ben reckons that instead of forecasting, a more precise analysis in terms of implications
for what to do with estimated factors in a FAVAR context is better

## Threshold Chapter

Far future - will need to sit down and discuss with Ben what sort of policy analysis options
the disentanglement procedure could be used for

## CWF Project

The closest related literature is actually from the finance literature dealing with
portfolio optimization

The novelty of this paper is likely going to be:

- Use of something from finance and apply it in forecast aggregation
- Use of a GMM like framework to consistently estimate the correct weights
- Apparently the literature has not actually focused on correctly estimating the weights, 
and is instead focused on just minimizing variance - this is not the same!
- A forecast aggregation framework which allows for a large number of aggregate models - 
mirrors a large panel of stocks.

Worst case scenario, this ends up being just an applied paper

Difficulties:

- Actually coming up with a large number of models to estimate
- Carve the code for Honours thesis for FFORMA, which has a fairly large number of models, 
which are not too hard to run
- Need to look into/implement possibly a factor structure for the residuals, in order to
invert the covariance matrix

## HCR Project and Paper 3

Code is currently running on HPC - will need to check on it

Paper 3 with NOBS = 10,000 is taking exponentially more time...

Not sure why - hopefully not an error