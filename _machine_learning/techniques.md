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
