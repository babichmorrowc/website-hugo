---
title: "[Poster] Quantifying species tolerances and functional diversity using n-dimensional hypervolumes: a comparison of methods"
date: 2017-01-01
draft: false
author: "Cecina Babich Morrow, Benjamin Blonder, Brian Maitner, Brian Enquist, Andrew Kerkhoff"
summary: "Poster comparing different hypervolume methods for ecological applications."
subtitle: "Comparison of two methods for creating n-dimensional hypervolume methods."

# Name of event and optional event URL.
event: "International Biogeography Society 2017"
# event_url: "https://example.org"

# Location of event.
location: "Tucson, AZ"

# Is this a selected talk? (true/false)
selected: false

# Projects (optional).
#   Associate this talk with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects: ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects: []`.
projects: ["hypervolumes"]

# Tags (optional).
#   Set `tags: []` for no tags, or use the form `tags: ["A Tag", "Another Tag"]` for one or more tags.
tags: ["plant biodiversity", "BIEN", "hypervolume"]
categories: ["biodiversity", "BIEN", "hypervolume"]

# Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides: ""`.
# slides: "example-slides"
links:
- icon: images
  icon_pack: fas
  name: slides
  url: "https://www.researchgate.net/publication/317280284_Quantifying_species_tolerances_and_functional_diversity_using_n-dimensional_hypervolumes_a_comparison_of_methods"

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

> This poster was made using version 1.4.6 of the `hypervolume` R package. These results should not be considered representative of the current algorithms in the package - to see current algorithm performance, refer to [Blonder *et al.* 2017](https://babichmorrowc.github.io/publication/hypervolumes/).

Multidimensional hypervolumes enable ecologists to visualize the functional trait space occupied by an ecological community. Previously, hypervolumes have been measured using a minimum convex hull, but convex hulls are exclusively determined by extreme points and they cannot account for possible holes in the trait space. A multivariate kernel density estimation method with hyperbox kernels was proposed to deal with high-dimensional or holey datasets, but this method produces unrealistically blocky hypervolumes. We examined two alternatives: a Gaussian kernel density estimation method and a support vector machine method. We tested these two new methods and the hyperbox method by creating hypervolumes for three New World biomes using trait data from plants and mammals. We varied the parameters for each method in order to determine sensitivity to parameter variation. The resulting hypervolumes were compared with respect to their total volume, shape, and overlap. The hyperbox hypervolumes consistently had the largest volume of the three methods. The Gaussian method proved least sensitive to variation in bandwidth, while the support vector machine is the most customizable in terms of its two parameters, but may be susceptible to overfitting.
