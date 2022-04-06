---
id: BMClpTRP3V8ITqM7R4kh0
title: To Do List
desc: ''
updated: 1648508528830
created: 1635455071285
---

Broad TODO list of things to do - revisit and keep updated!

## DFM Package

The main backend of everything. 

Make this focused and very good at estimating factor models via PCA.

You will need to code up forecasting related functions later on - this will be the main sell of this program.

### Other Factor Models

ALso will need to code up LFM and GDFM properly.

LFM is different and originally discarded, but now it is of somewhat interest.

Bin is very keen on this. Although Bonsoo is in the same boat as me and thinks this is a 
completely different model, it nevertheless is of interest to see a comparison.

Email sent to Liu and Zhang for replication code for their changepoint estimator for LFMs.

GDFM is also of low priority...

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