---
title: "Talk: Using SVMs to delineate parapatric ranges: An example with three-toed sloths (Bradypus)"
date: 2019-06-13
draft: false
date: 2019-06-13T11:30:00
author: "Cecina Babich Morrow"
subtitle: "Using support vector machines for range estimates of *Bradypus*."
summary: "Applying support vector machines to incorporate biotic information into range estimates for three species of *Bradypus*."

# Name of event and optional event URL.
event: "Helen Fellowship Final Presentation"
#event_url: "http://textengine.net/career-outreach-to-lgbt-young-adults/ "

# Location of event.
location: "New York, NY"

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
tags: ["species distribution modeling", "Bradypus", "machine learning"]
categories: ["species distribution modeling", "Bradypus", "machine learning"]

# Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides: ""`.
# slides: "example-slides"

# Links (optional).
url_pdf: ""
url_slides: ""
url_video: ""
url_code: ""

# Does the content use math formatting?
math: true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  # Caption (optional)
  caption: "Hybrid weighted support vector machine classifier"

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point: "Right"
  
---

Species distribution modeling (SDM) techniques are a common tool for estimating species ranges. These models typically rely only only on abiotic variables without accounting for biotic interactions, despite the fact that these interactions may impose important constraints on ranges. Distribution patterns in which closely-related parapatric species replace each other across geographic space are common in ecology. We sought to address whether incorporating biotic information into range estimates for three species of sloth (genus *Bradypus*) would improve distribution models for species demonstrating this parapatric pattern of distribution. We used support vector machines (SVMs) as masks to delineate the predicted boundaries between these three species' ranges. We created two different kinds of SVMs: 1) spatial SVMs using only occurrence data, and 2) sp+env SVMs using occurrence data in conjunction with predicted habitat suitability from SDMs. We found that the sp+env SVM resulted in the most ecologically realistic distribution model, accounting for contact zones between species and the effects of climate.

## Slides

{{< gslides src="https://docs.google.com/presentation/d/e/2PACX-1vT29X9rGoq1GeCwrXMPJEhmwy7I_nf8fFzpIMdWyLQfROI-zVqicELakhgOgRWvDgicV3s_c6ii4njc/embed?start=false&loop=false&delayms=3000" >}}

