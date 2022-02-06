---
layout: default
title: Random variables
---

# Random Variables 

## Table of discrete distributions 

<img width="746" alt="image" src="https://user-images.githubusercontent.com/57341225/152672412-08f9dde4-5189-456c-886d-82a9d46a2638.png">

[Source](https://web.stanford.edu/class/cs109/lectures/9-Continuous/9-Continuous.pdf).  

## Poisson 

Use Poisson when you are given a rate and care about the number of occurrences. For example, the number of requests in 5 minutes if the average request per minute is 3. Another use case is to approximate computationally expensive binomial random variables. 

### Approximation of binomial 

To approximate a binomial distribution using Poisson, define 

$$\lambda=n*p$$ 

where $$n$$ is the number of trials and $$p$$ is the probability of success for each trial. 

Do this when 

$$
\begin{aligned}
&n>20, p<0.05 \; or \;  \\
&n>100, p<0.1. 
\end{aligned}
$$

- Note: the approximation gets worse if $$n$$ is not very large and/or $$p$$ is not very small. 
- Poisson is also useful even when all the requirements aren't satisfied perfectly (e.g. probability varies slightly for each trial or number of successes isn't exactly independent). 

### Examples of Poissons 

- Number of entries in large hash table (since independence doesn't quite need to be satisfied). 
- Number of requests in a web server 
