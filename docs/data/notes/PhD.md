
Welcome to my website!

This website has been built using Dendron, and each topic has been collated into collapsible sections on the left hand side. Below is a high level overview showing how each section is connected for ease of navigation.



Dendron has incredibly powerful search functionality due to good indexing, even outside of working in raw .md files. Simply use the search bar at the top of the website to find something.

## Quick Links

[[roadmap]]

[[Meeting]]

[[TODO]]

## To do List

Type up Bai and Ng assumptions

Investigate Bates et al Assumptions

Investigate consistency of using an estimated break point in conjunction with BNIC
This seems to be consistent using k_tilde that itself may be Op(1)

Fix up BP test for better interface (low priority)

Implement simulated Andrews exp and mean Wald/LM tests

- look into RSpectra package (supposedly faster eigen)
- not sure whether to rename this to SFM or not (lots of legacy code that needs to be changed)

Data
Fix and clean data for 
- AUMD (on hold, need to find date index)
- FREDQD
- CANMD (should be straightforward)
- CANQD
- UKMD (should be straightforward)

Investigate further sources of time series that could be used during COVID

Implement truly dynamic factor models (Forni) using Dynamic PCA
- BIG task
- read into dynamic PCA
- read into testing no. of dynamic factors
- do not believe there is a literature focusing on breaks in the dynamic setup
- implement dynamic PCA
- implement testing no of factors, (look into ICshocks functions and make this interface better)
- implement testing no of factors using AW test

Implement BKW standard test (non sequential)

Fix up BKW test
- implement a general plot method which plots *something* on the y axis, but most importantly, date on the x axis with estimated break dates, and each partition labelled with the no. of factors as determined by some consistent estimator

Fix up BE test
- so that there is a consistent interface for accessing this



