---
title: "[Poster] Improving species range estimates for an arboreal species group with a parapatric distribution"
date: 2019-06-29
author: "Cecina Babich Morrow, Peter J. Galante, Jamie M. Kass, Mary E. Blair"
summary: "Using support vector machines to mask out biotically unsuitable areas improves species range estimates for *Bradypus*."
subtitle: "Using support vector machines to mask out biotically unsuitable areas improves species range estimates for *Bradypus*."

# Name of event and optional event URL.
event: "99th Annual Meeting of the American Society of Mammalogists"
event_url: "https://www.mammalmeetings.org/"

# Location of event.
location: "Washington, D.C."

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
tags: ["Bradypus", "species distribution modeling", "biogeography", "machine learning"]
categories: ["Bradypus", "species distribution modeling", "biogeography", "machine learning"]

links:
- icon: images
  icon_pack: fas
  name: slides
  url: "Mammalogy_poster.pdf"

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

Three-toed sloths (genus Bradypus) include three species distributed parapatrically across mainland Central and South America: B. variegatus, B. tridactylus, and B. torquatus. The distributions of these arboreal species are constrained by forest cover, as well as by the presence of their parapatric congeners. Traditional species distribution modeling (SDM) techniques typically rely on abiotic variables without accounting for the effects of competition on range boundaries. We sought to improve range predictions for Bradypus by using the ranges of the parapatric congeners to mask abiotic SDM range predictions. To account for the presence of parapatric species, we used support vector machines (SVMs) to delineate borders between ranges using occurrence data and predicted SDM habitat suitabilities for each species. We found that the SVM range estimates were more closely aligned with ecological expectations than those generated from unmodified species distribution model predictions. The SVM estimates were also less likely to include occurrences of parapatric species in the predicted range and better accounted for known contact zones between species. Finally, we masked the range estimates with a forest cover threshold calculated by temporally matching occurrence points with remotely sensed forest cover data. This mask quantified the differential effects of deforestation and habitat fragmentation across the three species’ ranges.
