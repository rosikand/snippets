---
layout: default
title: Save and load PyTorch model 
---

# Save (and load) PyTorch model 

Save a trained model (defined as `net`) weights:  

```python
torch.save(net.state_dict(), "intended_path.pth")  # use .pth extension 
```

Load it back in: 

Instantiate another instance of the model's class and then load back in. What you are really loading in is the model's weights. 

```python
net = ModelClass()
net.load_state_dict(torch.load("saved_model_path.pth"))
```


