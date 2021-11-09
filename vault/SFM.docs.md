---
id: 2gbkoMtG1AFSSvJ8bApzQ
title: Static Factor Model Implementation Docs
desc: ''
updated: 1636430695718
created: 1636430581104
---

All Static Factor Models are implemented via the DFM() function call, and its related methods. This is mostly for legacy reasons, and to remain consistent with the broader literature. 

Note that truly dynamic factor models are implemented using GDFM(), using Forni et al's nomenclature of *generalized* dynamic factor models. This is also consistent with their factorcpt package.