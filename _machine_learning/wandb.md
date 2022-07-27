---
layout: default
title: Weights and Biases (wandb)
---

# Weights and Biases (wandb)

Easy-to-use, structured experiment versioning tracker for ML projects. Quite simple to orchestrate with PyTorch. Here are some general notes. 

- The main structure of `wandb` is composed of **project** and **runs**. You create a project and everytime you e.g., train your model, create a new run. This will let you view all your runs at once on the web server. 


## `wand.init` 

Lots of what you specify here is what is relevant to your run. Some common things I like to do (view all options [here](https://docs.wandb.ai/ref/python/init)): 

```python

```

