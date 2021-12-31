---
layout: default
title: Probability - Kolmogorov axioms 
tags: mathematics
---

# Probability: Kolmogorov axioms  

Let $$(\Omega, \mathcal{F}, P)$$ be a probability space and let $$A$$ and $$B$$ be events in the event space $$\mathcal{F}$$ ($$A, B \in \mathcal{F}$$). The probability function, $$P$$, must satisfy the following axioms which we accept as truth. 

### Axiom 1
    
$$0 \leq \mathrm{P}(A) \leq 1$$ 
    
That is, the resulting probability of an event occurring must be a number between $$0$$ and $$1$$. 
    
### Axiom 2
    
$$P(\Omega)=1$$
    
That is, the probability that at least one of the elementary events in the sample space will occur is $$1$$ [1]. Logically, this means that an outcome from any trial of the experiment will be in the sample space, $$\Omega$$ meaning that all outcomes must be from the sample space, $$\Omega$$. Intuitively, this also means that the sum of the probabilities for each element in the sample space is equal to $$1$$.  
    
### Axiom 3
    
$$\mathrm{P}(A \text { or } B)=\mathrm{P}(A)+\mathrm{P}(B)$$ 
    
where $$A$$ and $$B$$ are mutually exclusive events (they cannot both occur at the same time meaning the sets are disjoint: an example is coin tossing. A trial can result in heads or tails but not both). In words, this means that the probability of $$A$$ or $$B$$ occurring is the sum between the probability that $$A$$ will occur and the probability that $$B$$ will occur. This generalizes beyond just two events [2]. Specifically, for any sequence of mutually exclusive events $$(E_1, E_2,...)$$:  
    
$$
P\left(\bigcup_{i=1}^{\infty} E_{i}\right)=\sum_{i=1}^{\infty} P\left(E_{i}\right). 
$$ 


Citations: 

[1] - [https://en.wikipedia.org/wiki/Probability_space](https://en.wikipedia.org/wiki/Probability_space)
[2] - Sheldon M Ross. A first course in probability. Pearson, 2014.

Also: CS 109 Course Reader 
