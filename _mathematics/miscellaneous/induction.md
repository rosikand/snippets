---
layout: default
title: Induction 
---

# Mathematical Induction 

Induction is a useful proof technique. An analogy is 

> Mathematical induction proves that we can climb as high as we like on a ladder, by proving that we can climb onto the bottom rung (the **basis**) and that from each rung we can climb up to the next one (the **step**). — _[Concrete Mathematics](https://en.wikipedia.org/wiki/Concrete_Mathematics "Concrete Mathematics")_, page 3 margins.

- Basically, you prove a base case (i.e. $$f(0)$$) and then you prove an inductive case: given that $$f(k)$$ works, we sow that $$f(k+1)$$ works. 
- Very useful for **algorithmic analysis**. Specifically, in courses such as CS 161, you will be asked to define an algorithm (i.e using pseudocode of some sort) and then prove that your algorithm works. The latter part is generally done through induction. 
	- That is, show that your algorithm works for some base case (i.e. the zero input). Then show that, if your algorithm works for some input $$k$$, then it works for the input $$k+1$$. 
		- Importantly, you aren't proving that your algorithm works for the input $$k$$. You are telling the reader to assume that bit and that what you actually prove is that, given this assumption, the input $$k+1$$ works. 
