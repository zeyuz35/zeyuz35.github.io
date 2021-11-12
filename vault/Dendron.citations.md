---
id: 1DyoojO5rIm0uTXOkxSuw
title: Citations
desc: ''
updated: 1636692826303
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

[[State_Space]]

This should not be too much of an issue for now, given that anything that needs to be properly rendered via pandoc shouldn't need cross document referencing anyway.

## Markdown Preview Enhanced

An outdated forked version of this is forked by Dendron and available, but seems to be abandoned.

Markdown Preview Enhanced is likely the most fully featured preview, but unfortunately does not seem to be working correctly.

In particular, changing the parser to pandoc (in order to get citations working) somehow makes it break with using KaTeX. Using MathJaX is janky and not entirely compatible. 

For this reason, the preferred method of previewing documents is via the Pandoc Markdown Preview extension, as the only feature that is not supported by this are Dendron's backlinks.
