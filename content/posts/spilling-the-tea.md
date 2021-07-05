+++
title = "Spilling the tea"
date = 2021-06-26T16:10:52+05:45
type = "post"
description = "A story of how data leakage ruined a competition"
in_search_index = true
[taxonomies]
tags = ["Data", "Data Pipelines","Kaggle"]
[extra]
og_preview_img = "/images/joplin-desktop.png"
+++
So there's currrently some drama in a kaggle competition. It looks like the organisers didnt properly prepare the validation/test set. This resulted in label leakage resulting in skewed results. As I stated in the previous post, data processing is key. In this post, I hope to go over the mistakes made. 

But first, a quick history....

#### SETI

{{ youtube(id="P_vTS46ivck" }}
