
## Technical Specifications

This is the master document for my PhD Thesis, investigating the issues that may arise from 
structural breaks, in the context of large macroeconomic factor models.

This document will be mostly documented within markdown files in an implementation/format 
known as Dendron, open source and most crucially allows for tagging, and creation of 
very complex linking and visualization.

It is also able to seamlessly weave together maths via KaTeX (or MathJax), simple diagrams
via mermaid, and at least represent code chunks. It is unable, however, to directly
interface with any programming languages, and should only serve as a notes guide and 
literature review tool.

Note that because GitHub pages only builds websites from /docs/ occasionally, there is a bit of lag for this to update once pushed.

## Current Limitations

### No Support for rendering Academic Citations

Dendron does not have any support for properly rendering academic citations. Markdown style compatible citations are supported by VScode extensions such as Pandoc citer, but these are rendered as actual links. 

Rendering the same .md file via a pandoc based program.

Therefore, for now, enter the citations in as you usually would. For something a bit more proper, you can simply render the same .md file using pandoc.

Issue has requested on GitHub:

[[https://github.com/dendronhq/dendron/issues/1605]]

[[https://github.com/dendronhq/dendron/issues/547]]

## No render/export to PDF

No functionality to render/export to PDF. Closest we have is to open the preview as a HTML file, then convert that to a PDF.

Similarly, the raw .md files can be rendered directly to .pdf via a pandoc approach. 

Advice: do everything in .md for now anyway.

## Narrow stylesheet

Built websites using Dendron have a narrow stylesheet by default, 

## No Code output

Dendron does not implement any ability to easily run/integrate code output, so annoyingly any output will need to be explicitly outputted from R, and inserted as "normal" images or tables. On the plus side, this is likely the approach I will have to go for more "proper" submissions using LaTeX proper anyway.

Advice: Keep code output separate, and save into a folder called "plots" or something, then directly insert them in .md files.

## LaTeX Macros

Most Pandoc preview/knitting has the latex_macros extension enabled by default.

Simply drop 

```
\newcommand{\sumT}{\sum_{t = 1}^{T}}
```

RAW near the start of the document to define any macros. 

## Building to website

Install the dendron CLI first

```
npm install -g @dendronhq/dendron-cli@latest
```

Run the command palette and follow the prompts to build for the first time. This required to clone the nextJS template.

Once this has been cloned once, publish your site (to GitHub) by running

```
dendron publish export --target github
```


