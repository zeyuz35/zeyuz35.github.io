---
id: PhD
title: PhD Homepage
desc: ''
updated: 1635319435721
created: 1595961348801
stub: false
---

Welcome to my website!

This website has been built using Dendron, and each topic has been collated into collapsible sections on the left hand side. Below is a high level overview showing how each section is connected for ease of navigation.

Furthermore, Dendron has incredibly powerful search functionality due to good indexing, even outside of working in raw .md files. Simply use the search bar at the top of the website to find something.

Below is meant to be an interactive view of how the notes are laid out, but this functionality has not been implemented yet.
## Technical Specifications

This is the master document for my PhD Thesis, investigating the issues that may arise from 
structural breaks, in the context of large macroeconomic factor models.

This document will be mostly documented within markdown files in an implementation/format 
known as dendron, open source and most crucially allows for tagging, and creation of 
very complex linking and visualization.

It is also able to seamlessly weave together maths via KaTeX (or MathJax), simple diagrams
via mermaid, and at least represent code chunks. It is unable, however, to directly
interface with any programming languages, and should only serve as a notes guide and 
literature review tool.

Note that because GitHub pages only builds websites from /docs/ occasionally, there is a bit of lag for this to update once pushed.

Dendron does not implement any ability to easily run/integrate code output, so annoyingly any output will need to be explicitly outputted from R, and inserted as "normal" images or tables. On the plus side, this is likely the approach I will have to go for more "proper" submissions using LaTeX proper anyway.
## Roadmap



## Meeting Summary

## To do List

Type up Bai and Ng assumptions

Investigate Bates et al Assumptions

Investigate consistency of using an estimated break point in conjunction with BNIC
This seems to be consistent using k_tilde that itself may be Op(1)

Fix up BP test for better interface (low priority)

Implement simulated Andrews exp and mean Wald/LM tests

Fix up DFM
- xts conversion DONE
- new eigen() DONE
- DFM.fit DONE
- vcov DONE
- svd() backend DONE, but turns out to be slower
- look into RSpectra package (supposedly faster eigen)
- not sure whether to rename this to SFM or not (lots of legacy code that needs to be changed)


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



