---
layout: default
title: Experimentation with config files 
---


# Using config files in your ML experiments 

It has become common to use `.yaml` files to specify experiment hyperparams when training your models. This is to increase reproducability, modularity, and efficiency when experimenting. 

Question: is their a standardized way to parse the yaml file or should one write a custom script to do it? Is their a standardized way to do this? How do you limit the things people can write in certain fields? What happens if your code evolves to include new field? Do the old config files become unusable? 

Cool thing: [YACS]([url](https://github.com/rbgirshick/yacs)) from Facebook. 

