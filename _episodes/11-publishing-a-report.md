---
exercises: 10 min
keypoints:
- 'R-Studio lets you Knit and Publish to R-pubs'
- Github has Github Pages
knit: '(function(inputFile, encoding) { out_dir \<- ''../\_episodes'';
  rmarkdown::render(inputFile, encoding=encoding,
  output_file=file.path(dirname(inputFile), out_dir,
  ''11-publishing-a-report.md'')) })'
objectives:
- Explore Different methods for publishing your paper
output:
  md_document:
    preserve_yaml: true
    variant: markdown
questions:
- 'How to publish your report?'
source: Rmd
teaching: 20 min
title: Publishing a Report
---

### 11.1 Rendering R Markdown script

Once you have your `.Rmd` document refined and the *Knit* output looks
good it is ready to publish. When using R-Studio the simplest option is
to publish to Rpubs.com. Notice the "Publish" button in the upper right
corner of your *Knit* output.

This is where you'll need an Rpubs account as mentioned in
[setup](#FIXME) for this workshop.

Click the publish button
![](../fig/r-studio-knit-publish-button-scrnshot.png)

and you'll be presented with the following panels:

![](../fig/11-r-studio-knit-publish-to-scrnshot.png)
![](../fig/11-r-studio-knit-publish-confirm-scrnshot.png)

At the end of the publish process your paper will be live on the
internet with a URL similar to: `https://rpubs.com/yourname/678624`

Html Other document types? 11.2 Publishing as website on Github\*

11.4 ??Converting RMarkdown to LaTeX??