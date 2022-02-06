---
layout: default
title: Random variables
---

# Random Variables 

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
&n>100, p<0.1
\end{aligned}
$$
