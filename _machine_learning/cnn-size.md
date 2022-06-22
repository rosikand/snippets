---
layout: default
title: Convolutional neural network shape and sizing 
---

# Convolutional neural network shape and sizing 

One of the tedious parts when working with constructing neural networks is figuring out the right shape and size given your inputs. This note summarizes this math as noted in the [CS231N notes](https://cs231n.github.io/convolutional-networks/). 

## Convolutional layer 
- Accepts a volume of size $$W_{1} \times H_{1} \times D_{1}$$ 
and requires four hyperparameters (specified as args into the conv layer API function): 
    - $K$: Number of filters 
    - $F$: Size of the filters 
    - $S$ stride 
    - $P$ the amount of zero padding 

and produces a volume of size $$W_{2} \times H_{2} \times D_{2}$$
- $W2=(W1−F+2P)/S+1$
- $H2=(H1−F+2P)/S+1$ (i.e. width and height are computed equally by symmetry) 
- $D2=K$ (i.e. number of filters used) 

**Choosing hyperparameters**: 
General rule of thumb: $$
F=3, S=1, P=1
$$
Also ensure that $P=(F-1) / 2$ to preserve input size.

## Pooling layer 

In CNN architectures, we usually insert a few pooling layers in between the convolutional layers. These are responsib le for reducing the spatial size of the input, therefore decreasing the number of parameters and preventing overfitting. As the CS 231N notes put it: "pool layers are in charge of downsampling the spatial dimensions of the input.". 

- Accepts a volume of size $$W_{1} \times H_{1} \times D_{1}$$ 
and requires two hyperparameters (specified as args into the pool layer API function): 
    - $F$: Kernel (filter) size. 
    - $S$: stride 

and produces a volume of size $$W_{2} \times H_{2} \times D_{2}$$ 
- $W_{2}=\left(W_{1}-F\right) / S+1$
- $H_{2}=\left(H_{1}-F\right) / S+1$
- $D_{2}=D_{1}$ 

General rule of thumb: $F=2, S=2$. 

Note: there are [many types of pool layers](https://pytorch.org/docs/stable/nn.html#pooling-layers). It is common to use `MaxPool2d`. 

## Activation functions 

Activation functions connect the output of a previous layer to the input of the next. See [here](https://machinelearningmastery.com/choose-an-activation-function-for-deep-learning/).   

In general, there are two main layers of a neural network where an AF might be applied: hidden layers and output layers. 

- For **hidden layers**, we tend to use `tanh`, `sigmoid`, or `ReLU`. For ConvNets, we tend to use `ReLU` and that is what we will use here. Regarding the size, `ReLU` leaves the size and shape of the input volume unchanged. 
- For **output layers**, we tend to use `linear`, `logistic (sigmoid)`, `softmax`. Our choice will depend solely on the task we are performing. For regression, we usually just output the value we are trying to predict directly using a linear layer/activation. For binary classification, we use a sigmoid activation. And for multi-class classification, we use a softmax activation. 

Machine learning mastery has a nice diagram for deciding: 

![image](https://user-images.githubusercontent.com/57341225/174954356-ac83deb5-3138-4e6f-ac3b-b5108ff943b3.png)

## Common architecture pattern 

```
INPUT -> [[CONV -> RELU]*N -> POOL?]*M -> [FC -> RELU]*K -> FC 
```

### Dropout 

It has become increasingly common to "drop out" a few neurons between layers to reduce overfitting (regularization). Such layers are called dropout layers. 

A dropout layer does not change the input size.
