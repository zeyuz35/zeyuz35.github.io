
Andrews (1993) derives a set of distributions and critical values for structural break tests. The tabulated critical values in these is referenced a lot. 

Andrews (1994) extends the idea of a supremum based test statistic to include a mean test and exponential test, and note that these may be more robust. Seemingly, in the literature people mostly focus on the supremum version, and note that the other two also agree with it. A set of tabulated critical values is also provided.

These two sets of critical values are used a lot, and due to computational intensity involved with formally simulating them, people are recommended to linearly interpolate these values. A new, crude interpolation implementation of this has made in R.

Hansen (1997) notices that the critical values are close to a chi-squared distribution, and proposes a much quicker way to calculate them, something similar to say a surface response regression.

Andrews (2003) then revises the original set of critical values, noticing that in some cases they were biased downwards for no apparent reason.

Finally, Estrella (2003) proposes a much quicker and more tractable way of getting these p values, and this should be the end of this tedious strand of literature.

Note that the main contemporary implementation of this is in strucchange using Hansen's approach, using a bunch of *hidden* functions, hence why these are not very well known. The documentation erroneously refers to these as supF, expF, and meanF distributions, but this is not precisely true, and they should be supWald, expWald, and meanWald distributions.

