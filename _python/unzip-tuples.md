---
layout: default
title: Unzip tuples into lists 
---

It is common in machine learning to process data into the form `(x,y),...,(x,y)` but sometimes you may want two seperate lists: one for feature vectors and another for labels: `[x,...,x], [y,...,y]`. 

[user647772](https://stackoverflow.com/questions/12974474/how-to-unzip-a-list-of-tuples-into-individual-lists) has a nice method: 

```python
>>> your_list = [(1,2), (3,4), (8,9)]
>>> [list(t) for t in zip(*your_list)]
[[1, 3, 8], [2, 4, 9]]
```
