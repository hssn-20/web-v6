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

At this stage it's pretty much a cliche that data scientists spend 80% of their time cleaning/processing data. This is essential work. The tasks differ based on the type of data you're dealing with but they share a few [commonalities](https://machinelearningmastery.com/data-preparation-for-machine-learning/) which are: 
> - Data Cleaning:  Identifying and correcting mistakes or errors in the data.
> - Feature Selection:  Identifying those input variables that are most relevant to the task.
> - Data Transforms:  Changing the scale or distribution of variables.
> - Feature Engineering:  Deriving new variables from available data.
> - Dimensionality Reduction:  Creating compact projections of the data 

In this post, I hope to provide a quick set of first steps you can take in your projects. Feel free to scroll to the bottom for links to other resources.

### Cleaning

![image](/images/ML_CYCLE.PNG)

Before data can be used, it must be processed. The steps of the data processing pipeline must be coded and documented fully. A good practice is to retain your original datasets and generate the final version via version controlled scripts. Another good practice is to set aside a portion for testing before [processing](https://www.kaggle.com/c/seti-breakthrough-listen/discussion/246772).

Prior to doing any steps, make sure to throughly understand, record and catalogue the data collection process. This will be important when it comes time to debug. 

#### Step 1 - Check for outliers & duplicates 

#### Step 2 - Check the missing data

#### Step 3 - 

#### The Conclusion & The Resources

#### Papers
[Graphical Models for Processing Missing Data](https://arxiv.org/pdf/1801.03583.pdf)

