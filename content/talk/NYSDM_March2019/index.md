+++
title = "[Talk] Using SVMs to model ranges of congeneric sloth species"
date = 2019-03-15T14:30:00

author = "Cecina Babich Morrow"

summary = "Incorporating biotic information to guide range estimates of three species of *Bradypus*."
subtitle = "Incorporating biotic information to guide range estimates of three species of *Bradypus*."

# Name of event and optional event URL.
event = "New York Species Distribution Modeling Meeting"
event_url = "http://textengine.net/career-outreach-to-lgbt-young-adults/ "

# Location of event.
location = "New York, NY"

# Is this a selected talk? (true/false)
selected = false

# Projects (optional).
#   Associate this talk with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects = ["bradypus"]

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["species distribution modeling", "Bradypus", "machine learning"]
categories = ["species distribution modeling", "Bradypus", "machine learning"]


# Does the content use math formatting?
math = true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  caption = "Sloth photos: James Morrow, Kevin Schafer, M.S. Pool - Green Heritage Fund Suriname"

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Right"
  
+++

Species distribution modeling (SDM) techniques are a common tool for estimating species ranges. These models typically rely only only on abiotic variables without accounting for biotic interactions, despite the fact that these interactions may impose important constraints on ranges. Distribution patterns in which closely-related parapatric species replace each other across geographic space are common in ecology. We sought to address whether incorporating biotic information into range estimates for three species of sloth (genus *Bradypus*) would improve distribution models for species demonstrating this parapatric pattern of distribution. We used support vector machines (SVMs) as masks to delineate the predicted boundaries between these three species' ranges. We created two different kinds of SVMs: 1) spatial SVMs using only occurrence data, and 2) sp+env SVMs using occurrence data in conjunction with predicted habitat suitability from SDMs. We found that the sp+env SVM resulted in the most ecologically realistic distribution model, accounting for contact zones between species and the effects of climate.

## Slides

{{< gslides src="https://docs.google.com/presentation/d/e/2PACX-1vS_w666eIt4-3dUI-z6iVlD08EphadvhGys2IarVUPk7QIdG3dn7opO1LLLeuM7vcb6j8k7_5nVOAef/embed?start=false&loop=false&delayms=5000" >}}

