---
layout: default
title: Loss functions 
---

# Loss functions 

Some notes on loss functions (theory + programming through NN libraries) and activation functions. 

## Cross entropy 

[Reference article](https://towardsdatascience.com/cross-entropy-loss-function-f38c4ec8643e)

Used for classification. 

![image](https://user-images.githubusercontent.com/57341225/177394667-6867660d-0d71-4780-9454-0981e6d3b543.png)

Have NN produce raw logits for each class (so last layer should contain $n$ neurons where $n$ is the number of classes). Softmax can either be embedded into the loss (as is the case in PyTorch + Jax) or can be an activation function after the last linear layer. Softmax will compress all inputs to between 0 and 1 and turn the logits into probabilities (such that the summation of all of them will result in 1, per probability axioms). The cross entropy loss then computes a difference between this vector ("distribution") and the one-hot encoded label vector. The diagram taken from the reference article sums this up best. 
