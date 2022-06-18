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
