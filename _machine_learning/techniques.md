---
layout: default
title: Toolbox of ML Techniques 
---

# Toolbox of ML Techniques  

In this snippet thread, I'll be posting a bunch of ML techniques. 

## Domain adaption 

Same goal as transfer learning but adds explicit feature extraction to make it better. Essentially, pre-train on large dataset (source domain) and fine-tune your architecture on a target distribution. But... first, find a feature extractor network (via ML too!... domain adverserial training) to apply to both domains to get them "in the same distribution".  

<img width="1266" alt="image" src="https://user-images.githubusercontent.com/57341225/184988433-02f68433-1827-4c05-b08a-cdd269ce7565.png"> 

Image [source](https://www.youtube.com/watch?v=8AKqH6V9kjE). 

#### Good references 
- [ML2021 week13 Domain Adaptation](https://www.youtube.com/watch?v=8AKqH6V9kjE) 
- https://stacks.stanford.edu/file/druid:nv775dt3762/JoyHsuBachelorsThesis.pdf
- https://github.com/zhaoxin94/awesome-domain-adaptation

## Masked image modeling for self-supervised pre-training 

Say you have a dataset consisting of many unlabeled samples but few labeled samples. A good idea would be to do some sort of pseudo-labeling process (semi-supervised learning). But this is really only feasible right now for simple tasks like classification. For dense tasks like detection or segmentation, it might be a good idea to pre-train the weights using the unlabeled parts of the data. But how so? Masked image modeling provides a method. 

#### Good references 
- https://github.com/huggingface/transformers/tree/main/examples/pytorch/image-pretraining
- https://arxiv.org/pdf/2111.09886.pdf
- https://arxiv.org/pdf/2111.06377.pdf




## Deep metric learning 

Let's say that...

**References**: 
- https://kevinmusgrave.github.io/pytorch-metric-learning/
- https://www.reddit.com/r/MachineLearning/comments/xc0tmt/comment/io2sdk1/?utm_source=share&utm_medium=web2x&context=3


## Image classification using CLIP 

Instead of traditionally classifying images using a black-box neural network, one new approach would be to leverage NLP annotations. This is common in clinical workflows where NLP annotations are provided naturally. Then, one can embed both the image and the text annotation into a high-dimensional space and use contrastive learning to predict positive/negative for the class. 

This method is described in the paper "Expert-level detection of pathologies from unannotated chest X-ray images via self-supervised learning". 




