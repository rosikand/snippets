---
layout: default
title: Random variables
---

# Random Variables 

## Table of discrete distributions 

<img width="746" alt="image" src="https://user-images.githubusercontent.com/57341225/152672412-08f9dde4-5189-456c-886d-82a9d46a2638.png">

[Source](https://web.stanford.edu/class/cs109/lectures/9-Continuous/9-Continuous.pdf).  

## Poisson 

[Wikipedia](https://en.wikipedia.org/wiki/Poisson_distribution) has some good information. 


> Definition: The Poisson distribution is a discrete probability distribution that expresses the probability of a given number of events occurring in a fixed interval of time or space if these events occur with a known constant mean rate and independently of the time since the last event ([Wikipedia](https://en.wikipedia.org/wiki/Poisson_distribution)). 


Use Poisson when you are given a rate and care about the number of occurrences. For example, the number of requests in 5 minutes if the average request per minute is 3. Another use case is to approximate computationally expensive binomial random variables. 

The key thing to know about the derivation of a Poisson is that it really is a large Binomial RV under the microscope. We get the probability $$p$$ via dividing the rate by the amount of time (make sure the units line up). Now how we get the number of trials if the unit is time? Well... discretize it! Divide the time into a very large number (approaching infinity) of rectangles (like what we do for integrals). That gives us our $$n$$. That is how Poisson is actually derived. See how this is really just a binomial with parameters $$p$$ and $$n$$? 


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

- Number of entries in large hash table (since independence doesn't quite need to be satisfied) 
- Number of requests in a web server 
- Number of hurdles jumped in 100 yards given 2.1 hurdles per 10 yards 
  - Poisson can also be used for other interval types other than time. 
- The number of meteorites greater than 1 meter diameter that strike Earth in a year
- The number of patients arriving in an emergency room between 10 and 11 pm
- The number of laser photons hitting a detector in a particular time interval
