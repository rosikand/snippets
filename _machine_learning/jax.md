---
layout: default
title: Jax
---

# Resources and stuff about the Jax ML framework 

## Resources for learning 

- Flax docs are good. Check out a simple lin reg example [here](https://flax.readthedocs.io/en/latest/notebooks/flax_basics.html#Linear-regression-with-Flax). 

## Ecosystem 

Useful packages/libraries: 

- Jax (provides primitives such as `jit`, `vmap`, `grad`, PRNG, PyTree, Numpy API) 
- Flax (NN library, built on top of Jax... layered)  
- Equinox (PyTree-based NN library) 
- dm_pix (useful image functions such as extracting patches for transformers) 


## Misc. notes 
- Models and parameters are separated from each other. The model class/structure is defined as a subclass (for Flax) of `linen.Module` (see API [here](https://flax.readthedocs.io/en/latest/flax.linen.html)). 
- PRNG key can be used to init model params (and more). Having the key ensures reproducability. Question: why can't we just use a seed like with PyTorch? 
- A **Pytree** is basically just a Python container (i.e. list, dict, or tuple) that holds non-container-type objects (called leaves). It is a way to manage state by grouping various things together. Common use case in the ML pipeline is to group together model params in a Pytree and then update them all at once during each step in the training loop. To update the Pytree-enclosed params, we can use `tree_map` which maps a function to the elements (leaves) contained in a Pytree. So in this case, we can apply an update rule (e.g., for gradient descent, stored as a function) to the Pytree params in one line of code. 
```python
# credit: flax docs 
params = jax.tree_map(lambda p, g: p - learning_rate * g, params, jax.grad(mse_loss)(params, x_samples, y_samples))
```
