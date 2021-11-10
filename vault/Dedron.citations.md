---
id: 1DyoojO5rIm0uTXOkxSuw
title: Citations
desc: ''
updated: 1636514221785
created: 1636511956938
---

Guide on how to get citations working.

As mentioned in Dendron limitations section, Dendron does not currently support native rendering of academic citations (either in built in preview mode, or built to website).

However, because Dendron just uses .md files files as a backend, it is possible to pass these to pandoc directly and knit them the "usual" way.

A workflow that is fairly efficient is to use Pandoc Citer + vscode-pandoc.

vscode-pandoc will require you adding in `--citeproc` in the pdf opt settings.

Pandoc Citer requires you to add 

```
geometry: margin=2cm
bibliography: [references.bib]
reference-section-title: References
```

to the front of every .md file YAML.

In the meantime, this means that the built website is very annoying and won't have the references properly rendered. 

This method *should* be futureproof, because pandoc can directly convert .md files to .tex files (in fact this is already what it does in the backend).

Note that however, pandoc is not perfect. Although Dendron links can be done with `[[]]`, pandoc does not render this correctly.

This should not be too much of an issue for now, given that anything that needs to be properly rendered via pandoc shouldn't need cross document referencing anyway.
