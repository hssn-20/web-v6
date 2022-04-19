+++
title = "DataWorld: Episode 2, XGBoost & Friends"
date = 2022-04-19T00:12:55+05:30
type = "post"
description = "Effectively making use of Gradient Boosted Decision Trees"
in_search_index = true
[taxonomies]
tags = ["XGB", "Model_creation", "Algorithm"]
[extra]
og_preview_img = "/images/Decision_Tree_Depth_2.png"
+++
I've been meaning to get back into writing for a while, however life has had other plans. To ease myself back in (and keep my sanity), the next few episodes will mostly consist of notes/reviews I've made over the past year. Feel free to skip to the bottom of this post if you just need the links/resources. Without further ado, I present GBDTs!

#### Gradient Boosted Decision Trees - overview
![image](https://hudsonthames.org/wp-content/uploads/2019/09/bagging-1.png "Bagging classifier by Proskurin Oleksandr")
GBDTs are a specific form of [boosting](https://arxiv.org/pdf/1403.1452.pdf). Boosting was first pioneered by Robert Schaphire and Yoav Freund, who've recieved the Godel Prize for their work. In our case, its sufficient to know that boosting works by leveraging weak learners into strong ones. This is done by iteratively applying base learners on training data. If trained on the same data, the two code snippets below would produce the same predictions:

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

```python 
from sklearn.ensemble import GradientBoostingRegressor
gbr = GradientBoostingRegressor(max_depth=2, n_estimators=2, random_state=2, learning_rate=1.0)
gbr.fit(X_train, y_train)
y_pred = gbr.predict(X_test)
```
#### When to use them
GBDTS are currently the industry standard when it comes to structured/tabular data, both for their ease of use and perfomence. In fact in most Kaggle competitions you'd be remiss not to use them, either as part of a [stacked](http://rasbt.github.io/mlxtend/user_guide/classifier/StackingCVClassifier/) [model](https://www.kaggle.com/code/hiro5299834/tps-jan-2022-blend-stacking-models) or in [conjuction](https://www.kaggle.com/code/chasembowers/sequence-postprocessing-v2-67-lb/notebook) with neural network embeddings. However GBDTs do have clear disadvantages when it comes to explainability, NLP or vision centric tasks. For those cases and a few others, a different model type would be more suitable. 

#### The Do's And The Don'ts
- Do use the correct scoring metrics. While an accuracy score of 99% sounds great, it probably isn't what you should be measuring when dealing with [highly imbalanced data](https://stats.stackexchange.com/questions/222558/classification-evaluation-metrics-for-highly-imbalanced-data). 
- Do create a holdout set. This is a step a lot of people in industry forget, however it pays dividends when you can objectively compare results across multiple models. 
- Do create a strong baseline model. A lot of people when modelling jump straight into feature engineering or hyperparamter optimisation without fully understanding their data. A baseline lets you know whats predictable before spending hours/days/weeks trying to do what mathematically isn't possible.
- Do consult domain experts. Another common error with data scientists is waiting a few weeks into a project before reaching out to cross functional team members, and that's usually just to figure why a column has been mislabelled. Don't be that person, reach out early and reach out often. Whatever implicit and explicit knowledge you can embed into the modelling stage will pay double or more in your results. 
- Do spend time feature engineering & hyperparamter optimisation. [Optuna](https://optuna.org/#code_examples) is currently my favourite library for doing hyperparamter optimisation, but find one that works for you. The important thing is to be scientific in your search. 
- Dont forget to try other model types. An ensamble of non-correlated models usually does better than a single model on its own. 
- Dont forget to set the weight paramater, if known beforehand. 

#### Conclusion 
Ok, so you probably read that list wondering where's the difference. Here's the secret, there isn't (except maybe in [results](https://arxiv.org/abs/2106.03253)). Although the underlying mechanism is different, the process of creating and validating GBDT models are no different to what you would do when creating regressions or random forests. So take your time, do your experiments, document those results and repeat. This is a science afterall. 



#### Sources / Resources
- [Hands-On Gradient Boosting with XGBoost and scikit-learn](https://github.com/PacktPublishing/Hands-On-Gradient-Boosting-with-XGBoost-and-Scikit-learn)
- [Hyperparam Optimisation Examples](https://github.com/rasbt/machine-learning-notes/tree/main/hyperparameter-tuning-methods)
- [Awesome XGBoost](https://github.com/dmlc/xgboost/tree/master/demo)
- [Gradient Boosted papers](https://github.com/benedekrozemberczki/awesome-gradient-boosting-papers)
