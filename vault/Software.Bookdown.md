---
id: dfB6JRk5URkjMorEglLFE
title: Bookdown
desc: ''
updated: 1638333436702
created: 1638323538556
---

## Using Bookdown

This is certainly the preferred method of actually writing the thesis/confirmation.

However, it is a fucking mess.

The preamble option only works for pdf outputs. This is problematic for trying to convert this to a html website which you can deploy.

Additionally, it imposes too much of a strict hierarchy. I.e. it is not straightforward to scale and add more and more subsections over time.

Changing between html and pdf formats is not as straightforward as it may seem.

Changing the output format by itself is not enough. 

You will need to change/remvoe _output.yml to the corresponding format, and back again. 

Recommend to just comment the relevant lines out, etc.

## YAML 

use this yaml:

```
title: "PhD"
author: "Ze Yu Zhong"
date: "`r Sys.Date()`"
documentclass: book
site: bookdown::bookdown_site
output: 
  bookdown::bs4_book:
    header_includes: |
      \newcommand{\convp}{\overset{p}{\to}}
      \newcommand{\convd}{\overset{d}{\to}}
bibliography: [references.bib, book.bib, packages.bib]
# url: your book url like https://bookdown.org/yihui/bookdown
# cover-image: path to the social sharing image like images/cover.jpg
description: |
  PhD Thesis 
biblio-style: apalike
csl: chicago-fullnote-bibliography.csl
```

Unfortunately this is a little janky, because it runs the header_includes once for each rmd file and is therefore redefining the same macros a lot

However, this is the only way I coul dget it to work consistently across both html and pdf formats