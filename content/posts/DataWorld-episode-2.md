+++
title = "DataWorld: Episode 2, XGBoost & Friends"
date = 2022-04-19T08:10:55+05:30
type = "post"
description = "Effectively making use of Gradient Boosted Trees"
in_search_index = true
[taxonomies]
tags = ["XGB", "Model_creation", "Algorithm"]
[extra]
og_preview_img = "/images/Decision_Tree_Depth_2.png"
+++```

I've been meaning to get back into writing for a while, however life had other plans. To ease myself back in (and keep my sanity), the next few episodes will mostly consist of notes/reviews I've made made reading. Feel free to skip to the bottom of this post if you just need the links/resources. Without further ado, I present XGBoost!

#### Gradient Boosted Decision Trees - overview and history.   
GBDTs are a specific form of [boosting](https://arxiv.org/pdf/1403.1452.pdf). Boosting was first pioneered by Robert Schaphire and Yoav Freund, they recieved the Godel Prize for their work. For our case, its suffiecient to know that boosting works by leveragig weak learners into strong ones. This is done by iteratively applying base learners on the training data. If trained on the same data, the two code snippets below would produce the same predictions:
Example 1 
```python 
from sklearn.tree import DecisionTreeRegressor
tree_1 = DecisionTreeRegressor(max_depth=2, random_state=2)
tree_1.fit(X_train, y_train)
y_train_pred = tree_1.predict(X_train)
y2_train = y_train - y_train_pred
tree_2 = DecisionTreeRegressor(max_depth=2, random_state=2)
tree_2.fit(X_train, y2_train)
y2_train_pred = tree_2.predict(X_train)
y1_pred = tree_1.predict(X_test)
y2_pred = tree_2.predict(X_test)
y_pred = y1_pred + y2_pred
```

Example 2 

```python 
from sklearn.ensemble import GradientBoostingRegressor
gbr = GradientBoostingRegressor(max_depth=2, n_estimators=2, random_state=2, learning_rate=1.0)
gbr.fit(X_train, y_train)
y_pred = gbr.predict(X_test)
```


#### Sources
- [Hands-On Gradient Boosting with XGBoost and scikit-learn](https://github.com/PacktPublishing/Hands-On-Gradient-Boosting-with-XGBoost-and-Scikit-learn)
- [Detecting and treating outliers in Python](https://towardsdatascience.com/detecting-and-treating-outliers-in-python-part-1-4ece5098b755)
- [Anomaly Detection Using Isolation Forest in Python](https://blog.paperspace.com/anomaly-detection-isolation-forest/)
- [Best-Practice Recommendations for Defining, Identifying, and Handling Outliers](https://journals.sagepub.com/doi/10.1177/1094428112470848)
- [A Comprehensive Study of the Past, Present, and Future of Data Deduplication](https://ieeexplore.ieee.org/abstract/document/7529062)
- [When to Impute? Imputation before and during cross-validation](https://arxiv.org/pdf/2010.00718.pdf)
- [New data preprocessing trends based on ensemble of multiple preprocessing techniques](https://www.sciencedirect.com/science/article/pii/S0165993620302740)
- [When and how should multiple imputation be used for handling missing data in randomised clinical trials – a practical guide with flowcharts](https://bmcmedresmethodol.biomedcentral.com/articles/10.1186/s12874-017-0442-1https://bmcmedresmethodol.biomedcentral.com/articles/10.1186/s12874-017-0442-1)
- [Toward Data Cleaning with a Target Accuracy:A Case Study for Value Normalization](https://arxiv.org/pdf/2101.05308.pdf)

