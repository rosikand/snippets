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

Note that the above saves the weights (separate from the model class). If you'd like to save the entire model class (with the weights encapsulated), PyTorch can do this too (but it is not recommended). See [here](https://pytorch.org/tutorials/recipes/recipes/saving_and_loading_models_for_inference.html#:~:text=A%20common%20PyTorch%20convention%20is,pth%20file%20extension) for more. 
