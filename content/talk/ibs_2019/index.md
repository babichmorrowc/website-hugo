---
title: "[Talk] Delineating parapatric ranges using species distribution models and support vector machines: An example with three-toed sloths (Bradypus)"
date: 2019-08-09T00:00:00
author: "Cecina Babich Morrow, Jamie M. Kass, Peter J. Galante, Robert P. Anderson, Mary E. Blair"
subtitle: "Using support vector machines to incorporate biotic information into the range estimates of parapatric species."
summary: "Applying support vector machines to refine range estimates for three species of *Bradypus*."

# Name of event and optional event URL.
event: "International Biogeography Society Humboldt Meeting 2019"
# event_url: "https://example.org"

# Location of event.
location: "Quito, Ecuador"

# Is this a selected talk? (true/false)
selected: false

# Projects (optional).
#   Associate this talk with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects: ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects: []`.
projects: ["bradypus"]

# Tags (optional).
#   Set `tags: []` for no tags, or use the form `tags: ["A Tag", "Another Tag"]` for one or more tags.
tags: ["species distribution modeling", "Bradypus", "biogeography"]
categories: ["species distribution modeling", "Bradypus", "biogeography"]
links:
- icon: images
  icon_pack: fas
  name: slides
  url: "BabichMorrow_IBS-Humboldt.pdf"

# Does the content use math formatting?
math: true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  # Caption (optional)
  # caption: "Image credit: [**Unsplash**](https://unsplash.com/photos/bzdhc5b3Bxs)"

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point: "Right"
  
---

Despite growing understanding that biotic interactions may impose important constraints on distributional limits, species distribution modeling (SDM) applications typically focus on abiotic variables without explicitly accounting for biotic interactions. One example of biotic influences on geographic ranges is the common phenomenon of closely related parapatric species replacing each other across geography. We sought to address whether incorporating biotic information via post-processing SDM outputs would improve distributional estimates for three sloth species in the genus Bradypus with parapatric ranges. In a novel approach, we used support vector machines (SVMs) to spatially classify map cells, indicating which of the species is most likely to be present. We then use the SVM output to mask the SDM suitability predictions by removing pixels that the SVM indicated as part of the range of a different species. We implemented two different types of SVMs: 1) purely spatial SVMs, using only occurrence data, and 2) spatial + environmental SVMs, using occurrence data in conjunction with SDM-predicted suitability values. After using the SVM outputs as masks, we found that both SVM implementations were less likely to include occurrence points of congeners in species’ predicted distributions than the unmodified SDM predictions. Further, we found that the spatial + environmental SVM resulted in distributional delimitations for contact zones that best matched our ecological expectations for these species. This approach could be widely applied both to pure macroecological studies as well as conservation and management, including IUCN Red Listing.
