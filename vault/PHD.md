---
id: e7agvwSYPTCFFLBPt99MC
title: PHD
desc: ''
updated: 1634221040995
created: 1634214042387
---

# PhD Thesis Master Document

This is the master document for my PhD Thesis, investigating the issues that may arise from 
structural breaks, in the context of large macroeconomic factor models.

This document will be mostly documented within markdown files in an implementation/format 
known as dendron, open source and most crucially allows for tagging, and creation of 
very complex linking and visualization.

It is also able to seamlessly weave together maths via KaTeX (or MathJax), simple diagrams
via mermaid, and at least represent code chunks. It is unable, however, to directly
interface with any programming languages, and should only serve as a notes guide and 
literature review tool.

## Todo List

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
- svd() backend

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