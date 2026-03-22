---
layout: archive
title: "Write The Manuscript On LaTeX/Overleaf"
permalink: /tips-write_manuscript/
author_profile: false
---

{% include base_path %}

I recommend to use [Overleaf](https://www.overleaf.com/) to save time for LaTeX environment setup, and to keep track of up-to-date progress among collaborators.

## Handy Packages

- [zebra-goodies](https://github.com/xueruini/zebra-goodies) for inline note-taking macros (`\todo`, `\note`) to explicitly highlight writing tasks.
- [changes](https://ctan.org/pkg/changes) for manually markup changes of text, such as additions, deletions, or replacements. This will be helpful for journal submission that needs the "marked changes" revision.

## Best Practices

- Use `sections/` folder to organize the manuscript. A CS/AI manuscript typically has the following sections:
  1. Introduction
  2. Related Work
  3. (Optional) Study Design
  4. Methods
  5. Experiments
  6. Conclusion
- The `Study Design` section is optional, but highly recommended when a novel dataset or research task is proposed (see my [BIBM'25 paper EpicAge](https://arxiv.org/abs/2511.07219)). It typically contains:
  1. A brief introduction to data source and cohort (samples used in the study)
  2. A formal mathmatical problem definition
- Use macro `\modelname` to define the proposed model's name `\newcommand{\modelname}[0]{\textsc{EpiCAge}\xspace}`. We often find that the `\modelname` can be changed time-to-time.
- Use `figures/` folder to store all figures in the manuscript. Prefer `.pdf` format for vector graphics to ensure quality in publication.

## How to Write A Lot
- Begin with the **outlines** of the manuscript (e.g., a list of subsections for each section), and then fill in the details. 
- Do not worry about the quality of writing at the beginning. The most important thing is to get the main ideas down on paper, and then refine the writing later.
- Begin with the `Study Design`, `Methods` and `Experiments` sections, which are typically more straightforward to write. Then move on to the `Introduction` and `Conclusion`, which often require more creativity and polish.
- Write each paragraph's punch line for the `Introduction` to convey the main message. This will be helpful when discussing with co-authors.