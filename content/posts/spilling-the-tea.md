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
There's currrently some [drama](https://www.kaggle.com/c/seti-breakthrough-listen/discussion/246772) in one of the kaggle competition. It looks like the [organisers](https://www.kaggle.com/c/seti-breakthrough-listen/discussion/246782) didn't properly prepare the test set, resulting in label leakage. As I stated in the previous post, data processing is key.Data leakages come in two forms. In this post, I hope to go over what a data leakage is and how to generaly avoid it. 

But first, a quick history of SETI....

{{ youtube(id="P_vTS46ivck") }}
