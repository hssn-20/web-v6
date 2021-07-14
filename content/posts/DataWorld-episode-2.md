+++
title = "DataWorld: Episode 2, Feature Selection"
date = 2021-06-30T12:10:52+05:45
type = "post"
description = "Selecting which features to use"
in_search_index = true
[taxonomies]
tags = ["Data", "Feature-Selection"]
[extra]
og_preview_img = "/images/joplin-desktop.png"
+++

In this post I hope to provide what steps you can take when doing feature selection. 

#### Variance

Simplest step that can taken is to remove features with very low variance. This because they are close to being constant so will probably not add any model. Scikit-learn provides an implmentation. 

#### Correalation 

You can also remove features with high correalation. For calculating correlation between numerical values you can use the Pearson correlation. 

####  Univariate feature selection 

#### Multivariate feature selection

#### Model based feature selection

- Greedy feature selection
