+++
title = "Data preperation: Episode 1"
date = 2021-06-23T08:10:55+05:30
type = "post"
description = "Basics of data preperation."
in_search_index = true
[taxonomies]
tags = ["Data", "Cleaning"]
[extra]
og_preview_img = "/images/joplin-desktop.png"
+++
![image](https://raw.githubusercontent.com/chiphuyen/ml-interviews-book/master/contents/images/image1.png)

At this stage it's pretty much a cliche that 80% of the job of a data scientist is data cleaning/processing. For a large part of a data projects' life, processing is essential.The tasks differ based on the type of data you're dealing with but they share a few [commonalities](https://machinelearningmastery.com/data-preparation-for-machine-learning/) which are: 
> - Data Cleaning:  Identifying and correcting mistakes or errors in the data.
> - Feature Selection:  Identifying those input variables that are most relevant to the task.
> - Data Transforms:  Changing the scale or distribution of variables.
> - Feature Engineering:  Deriving new variables from available data.
> - Dimensionality Reduction:  Creating compact projections of the data 

In this post, I hope to provide a quick set of first steps you can take in your projects. Feel free to scroll to the bottom for links to other resources.

## Cleaning

![image](/images/ML_CYCLE.PNG)

Before data can be used, it must be processed. The steps of the data processing pipeline must be coded and documented fully. A good practice is to retain your original datasets and generate the final version via version controlled scripts. Another good practice is to set aside a portion for testing before [processing](https://www.kaggle.com/c/seti-breakthrough-listen/discussion/246772).


## Missing & miscoded 

Joplin is 100% FOSS and is actively developed by [`@laurent22`](https://github.com/laurent22/) and a few other regular contributors. I contribute `$5/mo` to laurent22 via Github Sponsors. It's more or less the same amount that most note-taking apps charge for personal use as well, so this is just me expressing gratitude for building such a lovely software for the world to use it. I'm not sure of the motivations of `laurent22` behind building this and I don't wanna incorrectly assume anything either, but I guess some amount of financial incentive makes the whole deal sustainable for the open-source ecosystem.

Thanks for reading! It's been around a year that I am using Joplin and I posted this blog post only after really really using it a lot.

I'd love to know about your note-taking setups too, so please reach out to me on the usual channels that I'm available on and feel free to discuss!

Fin!

#### (Bonus Section) Why Not Obsidian

Yes, Obsidian is comparable to Joplin in a lot of ways. However there's a term in the [license](https://obsidian.md/eula) of Obsidian for personal use that makes it **impossible** to use it for your work stuff:

> You need to pay for Obsidian if and only if you use it for revenue-generating, work-related activities in a company that has two or more people. Get a commercial license for each user if that's the case

I don't have a problem for "paying" for software but such kinda licenses are just BS.
