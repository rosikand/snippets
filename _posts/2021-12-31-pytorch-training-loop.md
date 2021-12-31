---
layout: default
title: PyTorch training loop (and plot)
tags: machine-learning
---

# PyTorch training loop (and plot) 

Simple PyTorch training loop code adapted from the [docs](https://pytorch.org/tutorials/beginner/blitz/cifar10_tutorial.html#test-the-network-on-the-test-data). 

Model is defined as `net`. 

```python
EPOCHS = 50  # num epochs 
epoch_num = 0
loss_vals = []

for epoch in range(EPOCHS):  # loop over the dataset (EPOCHS) times 
    epoch_num += 1
    running_loss = 0.0
    
    for i, data in enumerate(trainloader, 0):
        # get the inputs; data is a list of [inputs, labels]
        inputs = data[0]  # add .to(device) if training on GPU 
        labels = data[1]  # add .to(device) if training on GPU 

        # zero the parameter gradients
        optimizer.zero_grad()

        # forward + backward + optimize
        outputs = net(inputs) 
        loss = criterion(outputs, labels) 
        loss.backward()
        optimizer.step()

        running_loss += loss.item() 

    print("Loss for epoch " + str(epoch_num) + ":", running_loss)
    loss_vals.append(running_loss)
    
print('Finished Training')
```

## Plotting loss values 

We can plot the loss value at each epoch from the `loss_vals` array like so: 

```python
# graph training loss 
import matplotlib.pyplot as plt 
import matplotlib.image as mpimg

plt.plot(loss_vals)
plt.title('Training Loss')
plt.ylabel('loss')
plt.show()
```
