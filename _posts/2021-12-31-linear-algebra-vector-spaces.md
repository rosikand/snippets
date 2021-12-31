---
layout: default
title: Linear algebra - vector spaces 
tags: mathematics
---

# Linear algebra - vector spaces

Definitions and theorems regarding finite-dimensional vector spaces. Most of these are adapted from [1]. See 3Blue1Brown's [video](https://www.youtube.com/watch?v=k7RM-ot2NWY) for intuition. 
 

  <u><b>Definition of linear algebra</b></u>: Linear algebra is the study of *linear maps* on finite-dimensional *vector spaces* [1].
  
  <u><b>Vector space</b></u>: A vector space is a set $$V$$ which contains vectors in space where the properties of commutativity, associativity, additive identity, additive inverse, multiplicative identity, distributive properties hold (closed under these properties).   
  

You should think of a vector space as a set of vectors with added structure/properties. 


  <u><b>Linear combination</b></u>: If $$a_{1}, \ldots, a_{m}$$ are $$n$$-vectors, and $$\beta_{1}, \ldots, \beta_{m}$$ are scalars, the $$n$$-vector

$$
\beta_{1} a_{1}+\cdots+\beta_{m} a_{m}
$$

is called a linear combination of the vectors $$a_{1}, \ldots, a_{n}.$$ The scalars $$\beta_{1}, \ldots, \beta_{m}$$ are called the coefficients of the linear combination. 


You should think of linear combinations as adding and scaling vectors to get a different vector. In fact, In other words, a vector in a vector space can be defined by how much it *scales* the unit (basis) vectors (which is shown mathematically through a linear combination). 


  <u><b>Basis</b></u>: A basis of a vector space $$V$$ is a set of vectors $$\left\{v_{1}, \ldots, v_{n}\right\}$$ such that each vector $$v \in V$$ can be written uniquely as a linear combination of $$v_{1}, \ldots, v_{n}.$$ 
  

Note: every basis of a vector space $$V$$ has the same length. 


  <u><b>Span</b></u>: The set of all linear combinations of a list of vectors $$v_{1}, \ldots, v_{m}$$ (i.e. vector space) in $$V$$ is called the span of $$v_{1}, \ldots, v_{m}$$, denoted $$\operatorname{span}(\left.v_{1}, \ldots, v_{m}\right).$$ In other words,
$$
\operatorname{span}\left(v_{1}, \ldots, v_{m}\right)=\left\{a_{1} v_{1}+\cdots+a_{m} v_{m}: a_{1}, \ldots, a_{m} \in \mathbb{R}\right\}
$$  
  </markdown> 
</blockquote>

In english, a *span* of a vector space is the set all of the possible
vectors one can obtain from forming linear combinations with the basis vectors of that vector space. 

<blockquote style="border: 0.9px solid rgb(102, 102, 102); padding: 10px; background-color: rgb(255, 255, 255);">
  <markdown>
  <u>**Dimension**</u>: A dimension of a vector space $$V$$ is the length of any basis of $$V$$ [1]. 
  </markdown> 
</blockquote>

All of this is nicely tied together with the most important definition: 

<blockquote style="border: 0.9px solid rgb(102, 102, 102); padding: 10px; background-color: rgb(255, 255, 255);">
  <markdown>
  <u>**Linear independence**</u>: A list $$v_{1}, \ldots, v_{m}$$ of vectors in $$V$$ is called linearly independent if the only choice of $$a_{1}, \ldots, a_{m} \in \mathbf{F}$$ that makes $$a_{1} v_{1}+\cdots+a_{m} v_{m}$$ equal 0 is $$a_{1}=\cdots=a_{m}=0$$. If the list $$v_{1}, \ldots, v_{m}$$ of vectors is not linearly independent, it is considered linearly dependent. 

In other words, a list of vectors is linearly independent if and only if all of them cannot be written as a linear combination of the others.  

  </markdown> 
</blockquote>


<blockquote style="border: 0.9px solid rgb(102, 102, 102); padding: 10px; background-color: rgb(255, 255, 255);">
  <markdown>
  <u>**Independence-dimension inequality**</u>: no list of vectors that is larger than the size of the smallest basis (another list of vectors) can be linearly independent (Length of linearly independent list $$\leq$$ length of spanning list).

  </markdown> 
</blockquote>


Linear transformations (maps) are functions that map one vector space to another (where the transformation is linear). The following definition is adapted from [1]. 

<blockquote style="border: 0.9px solid rgb(102, 102, 102); padding: 10px; background-color: rgb(255, 255, 255);">
  <markdown>
  <u>**Linear map**</u>: A *linear map* from $$V$$ to $$W$$ is a function $$F: V \rightarrow W$$ where the following properties hold (these properties are what make the transformation linear): 
  - **Additivity**: 
  $$
  F(u+v)=F(u) + F(v) \text { for all } u, v \in V
  $$
  - **Homogeneity**: 
  $$
  F(\lambda v)=\lambda(F v) \text { for all } \lambda \in \mathbb{R} \text { and all } v \in V
  $$

  </markdown> 
</blockquote>





[1] - Sheldon Jay Axler. Linear algebra done right. Vol. 2. Springer, 1997. 

