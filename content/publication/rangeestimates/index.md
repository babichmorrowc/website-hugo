---
title: "Operationalizing expert knowledge in species’ range estimates using diverse data types"
date: 2022-04-18T00:00:00
draft: false

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
author: 'Cory Merow, Peter Galante, Jamie Kass, Matthew Aiello-Lammens, Cecina Babich Morrow, Beth Gerstner, Valentina Grisales Betancur, Alex Moore, Elkin Noguera-Urbano, Gonzalo Pinilla-Buitrago, Jorge Velásquez-Tibatá, Robert Anderson, Mary Blair'

# Publication type.
# Legend:
# 0: Uncategorized
# 1: Conference paper
# 2: Journal article
# 3: Preprint / Working Paper
# 4: Report
# 5: Book
# 6: Book section
# 7: Thesis
# 8: Patent
publication_types: ["2"]

# Publication name and optional abbreviated version.
publication: "In *Frontiers of Biogeography*."
publication_short: "In *Frontiers of Biogeography*."

# Abstract and optional shortened version.
abstract: "Estimates of species’ ranges can inform many aspects of biodiversity research and conservation-management decisions. Many practical applications need high-precision range estimates that are sufficiently reliable to use as input data in downstream applications. One solution has involved expert-generated maps that reflect on-the-ground field information and implicitly capture various processes that may limit a species’ geographic distribution. However, expert maps are often subjective and rarely reproducible. In contrast, species distribution models (SDMs) typically have finer resolution and are reproducible because of explicit links to data. Yet, SDMs can have higher uncertainty when data are sparse, which is an issue for most species. Also, SDMs often capture only a subset of the factors that determine species distributions (e.g., climate) and hence can require significant post-processing to better estimate species’ current realized distributions. Here, we demonstrate how expert knowledge, diverse data types, and SDMs can be used together in a transparent and reproducible modeling workflow. Specifically, we show how expert knowledge regarding species’ habitat use, elevation, biotic interactions, and environmental tolerances can be used to make and refine range estimates using SDMs and various data sources, including high-resolution remotely sensed products. This range-refinement approach is primed to use various data sources, including many with continuously improving spatial or temporal resolution. To facilitate such analyses, we compile a comprehensive suite of tools in a new R package, maskRangeR, and provide worked examples. These tools can facilitate a wide variety of basic and applied research that requires high-resolution maps of species’ current ranges, including quantifications of biodiversity and its change over time."
summary: "Workflow for making and refining species range estimates, introducing a new R package, `maskRangeR`."

# Is this a selected publication? (true/false)
selected: false

# Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects: ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects: []`.
projects: ["bradypus"]

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides: ""`.
# slides: "example-slides"

# Tags (optional).
#   Set `tags: []` for no tags, or use the form `tags: ["A Tag", "Another Tag"]` for one or more tags.
tags: ["species distribution modeling", "biogeography", "R"]
categories: ["species distribution modeling", "biogeography", "R"]

# Links (optional).
links:
- icon: file
  icon_pack: fas
  name: Publication
  url: https://escholarship.org/uc/item/3m7719vv

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
# links: [{name: "Custom Link", url: "http://example.org"}]

# Digital Object Identifier (DOI)
doi: "10.21425/F5FBG53589"

# Does this page contain LaTeX math? (true/false)
math: true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  # Caption (optional)
  caption: "An overview of the steps in the maskRangeR workflow (Figure 1)."

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point: ""
---

## Abstract

Estimates of species’ ranges can inform many aspects of biodiversity research and conservation-management decisions. Many practical applications need high-precision range estimates that are sufficiently reliable to use as input data in downstream applications. One solution has involved expert-generated maps that reflect on-the-ground field information and implicitly capture various processes that may limit a species’ geographic distribution. However, expert maps are often subjective and rarely reproducible. In contrast, species distribution models (SDMs) typically have finer resolution and are reproducible because of explicit links to data. Yet, SDMs can have higher uncertainty when data are sparse, which is an issue for most species. Also, SDMs often capture only a subset of the factors that determine species distributions (e.g., climate) and hence can require significant post-processing to better estimate species’ current realized distributions. Here, we demonstrate how expert knowledge, diverse data types, and SDMs can be used together in a transparent and reproducible modeling workflow. Specifically, we show how expert knowledge regarding species’ habitat use, elevation, biotic interactions, and environmental tolerances can be used to make and refine range estimates using SDMs and various data sources, including high-resolution remotely sensed products. This range-refinement approach is primed to use various data sources, including many with continuously improving spatial or temporal resolution. To facilitate such analyses, we compile a comprehensive suite of tools in a new R package, maskRangeR, and provide worked examples. These tools can facilitate a wide variety of basic and applied research that requires high-resolution maps of species’ current ranges, including quantifications of biodiversity and its change over time.

