
[@barigozzi_quasi_2020] provides a strong theoretical results for the EM estimator, as viewed as a QML estimator.

Very standard inferential results are available, using the direct asymptotic results. Unfortunately, the sorts of tests that are available are very limited in scope at time of writing. 

Specifically, tests such as 

$$
H_0: \lambda_i = \lambda_j
$$

for two different *sets* of loadings, which imply $r$ restrictions (recall that there are in total $r$ loadings for each variable).

This practically isn't actually too useful - mostly there for testing whether two sets of loadings are the same or not. This could actually already be done with the standard [@bai_inferential_2003] PC inferential results. However, the QML method links the state space framework, and this could potentially be more flexible in the future.

It is unclear whether these sorts of inferential results can be extended to to include a structural stability test. 

Presumably, such a test would entail modifying the EM algorithm to include a dummy variable for time, resulting in a structural break specification. 

The log likelihood from a restricted vs unrestricted model could then be tested, or something similar. However, unclear whether this is asymptotically valid.

