+++
title = "DataWorld: Episode 1, Cleaning"
date = 2021-06-23T08:10:55+05:30
type = "post"
description = "Cleaning a basic dataset"
in_search_index = true
[taxonomies]
tags = ["Data", "Cleaning"]
[extra]
og_preview_img = "/images/joplin-desktop.png"
+++
![image](https://raw.githubusercontent.com/chiphuyen/ml-interviews-book/master/contents/images/image1.png "ML Cycle by Chip Huyen")

It's a cliche that data scientists spend 80% of their time cleaning/processing data. Although it can be tedious at times, this is essential work. The tasks  differ for every dataset you're dealing with but they share a few [commonalities](https://machinelearningmastery.com/data-preparation-for-machine-learning/) which are: 
> - Data Cleaning
> - Feature Selection
> - Data Transforms
> - Feature Engineering
> - Dimensionality Reduction

In this post, I hope to provide a quick set of steps you can take when cleaning a simple dataset.

#### Step 0 - Document  
![image](/images/ML_CYCLE.PNG "Produced by Pablo Duboue")
Before data can be used in most machine learning projects, it must be processed. For example, in a computer vision project image sizes will need to be standardised. It's best the steps taken during the data processing pipeline be coded and documented fully. A good practice is to retain your original dataset and generate the final version via version controlled scripts. Another good practice is to set aside the validation set before [processing](https://www.kaggle.com/alexisbcook/data-leakage).

Prior to doing any steps, make sure to throughly understand, record and catalogue the data collection process. You need to be able to answer questions like what sensors/forms/surveys were used, how is the data stored, how was the data [labelled](https://github.com/heartexlabs/awesome-data-labeling), who collected the data etc. This will be important when it comes time to debug. 

#### Step 1 - Check for duplicates & outliers 
Although it's fairly straight forward to [remove duplicates](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.drop_duplicates.html), it's also easy to do it without being cognizant of context. Remember to check the type/number of duplicates before removal. 

There a lot of different ways of defining an outlier, a common definition is; any data point that's significantly different from a given population. What is meant by 'significant' really depends on your dataset.  A reasonable algorithm for most cases is an [IsolationForest](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.IsolationForest.html).   
 
#### Step 2 - Check the missing data
What type of data is missing? Is it miscoded? How is the missing data labelled(NaN, N/A, Null or something else)? Is it missing completely at random or is the missingness specific? What is the structure of the missing information? These are just a few of the questions you should be able to answer. The [missingno](https://github.com/ResidentMario/missingno) library provides a quick way to visualise the missing data and hopefuly begin to answer some of those questions. 
#### Step 3 - Impute 
Scikit-learn [provides](https://scikit-learn.org/stable/modules/impute.html) a few functions that can be used to impute missing values however this step isn't always [necessary](https://www.paultwin.com/wp-content/uploads/Lodder_1140873_Paper_Imputation.pdf) as you can get away with listwise or pairwise deletion for certain datasets. The question of when that is the case really depends on domain. 
#### Conclusion 
So to conclude, when dealing with a new dataset: 
- Check duplicates
- Check outliers
- Check the missing data
- Impute(or not)

#### Sources
- [Graphical Models for Processing Missing Data](https://arxiv.org/pdf/1801.03583.pdf)
- [Detecting and treating outliers in Python](https://towardsdatascience.com/detecting-and-treating-outliers-in-python-part-1-4ece5098b755)
- [Anomaly Detection Using Isolation Forest in Python](https://blog.paperspace.com/anomaly-detection-isolation-forest/)
- [Best-Practice Recommendations for Defining, Identifying, and Handling Outliers](https://journals.sagepub.com/doi/10.1177/1094428112470848)
- [A Comprehensive Study of the Past, Present, and Future of Data Deduplication](https://ieeexplore.ieee.org/abstract/document/7529062)
- [When to Impute? Imputation before and during cross-validation](https://arxiv.org/pdf/2010.00718.pdf)
- [New data preprocessing trends based on ensemble of multiple preprocessing techniques](https://www.sciencedirect.com/science/article/pii/S0165993620302740)
- [When and how should multiple imputation be used for handling missing data in randomised clinical trials ??? a practical guide with flowcharts](https://bmcmedresmethodol.biomedcentral.com/articles/10.1186/s12874-017-0442-1https://bmcmedresmethodol.biomedcentral.com/articles/10.1186/s12874-017-0442-1)
- [Toward Data Cleaning with a Target Accuracy:A Case Study for Value Normalization](https://arxiv.org/pdf/2101.05308.pdf)

