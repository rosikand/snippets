---
layout: default
title: Core probability
---

# Core Probability 

## Equally likely outcomes 

If each outcome in the sample space is equally likely (e.g. heads or tails on a coin flip): 

$$
\mathrm{P}(E)=\frac{\text { number of events in S that contain E }}{\text { number of outcomes in } S}=\frac{|E|}{|S|}.
$$

This makes heavy use of combinatorical counting. 

## Probability of "or"
Let $A$ and $B$ be events. Say we want to know the probability of $A$ or $B$ occurring? 


> We ask "are the events mutually exclusive". 

### Mutually exclusivity 

Two events are considered to be mutual exclusive if, when in the same universe, both cannot occur at the same time. Set notationally, $A \cap B=\emptyset$. 

If $A$ and $B$, then the probability of "or" between them is: 

$$
P(A \text{ or } B) = P(A) + P(B)
$$

Note: if they are both equally likely, just sum all events and divide by size of the sample space. 

If $A$ and $B$ are *not* mutually exclusive, then we use the inclusion-exclusion formula. 

### Inclusion-exclusion formula 
If $A$ and $B$ are two non-mutually exclusive events, then the probability of "or" between them is: 












## Probability of "and" 


## Conditional probability and Bayes' Theorem 

Often times, we are concerned with questions of the form: "what is the probability of $A$ given that $B$ has occurred?". 

### Chain rule 

#### Showing independence 

By the rules above, it follows that two events are independent if 

$$
P(A|B) = P(A)
$$

### Bayes' theorem 

Useful when you know $P(B|A)$ but not $P(A|B)$. Answers how we "update" our beliefs on something given new information. 






### Diagram 

Summing everything up... 
![[Pasted image 20220203182206.png]]

Source: https://web.stanford.edu/class/cs109/lectures/5-Independence/5-Independence.pdf


## Common paradigms 

### DeMorgan's law 

Often times, it is easier to calculate the *inverse* of what we want. For example, given some large number of non-mutually exclusive events, instead of calculating the probability of "or" via the inclusion-exclusion theorem, it could be easier to inverse the problem. That is, make it a probability of "and" question and simply subtract $1$ from the multiplications of the opposite if the events are independent.  

#### "and" to "or"
Useful when mutliple events are not mutually exclusive (to avoid inclusion-exclusion) 

$$
\begin{aligned} P(E \text{ or } F) &= 1-P\left((E \text{ or } F)^{C}\right) \\ &= 1 - P\left(E^{C} \text{ and } F^{C}\right) \end{aligned}
$$

#### "and" to "or"

$$
\begin{aligned} P(E \text{ and } F) &=1-P\left((E \text{ and } F)^{C}\right) \\ &=1-P\left(E^{C} \text{ or } F^{C}\right) \end{aligned}
$$



### "At least one" 
Usually, this is the most useful case of DeMorgan's law. Just take the probability of "not all" do 1 minus this number. 

### "At least $n$" 

This is a generative process. Say we want to know the probability of at least $$2$$ things occurring when there are $$4$$ total objects. We simply take the sum of exactly $$2$$ things ocurring + prob of $$3$$ things occurring + prob of $$4$$ things occurring. 

Useful to use binomial random variables here. 

### "Exactly $k$ out of $n$"

$$
\left(\begin{array}{l}n \\ k\end{array}\right) * (prob \; yes)^{k} \cdot (prob \; not)^{n-k}  
$$

Python function: 

```python
def exact_k(prob, k, n):
	# helper function that calculates 
	# that exactly k of n events occur 
	# given prob of occurring. 

	binom = math.comb(n, k)
	prob_yes = math.pow(prob, k)
	prob_no = math.pow((1 - prob), (n - k))
	result = binom * prob_yes * prob_no
	return result 
```

### General problem solving strategy 

DRAW OUT EVENTS! Explicitly model what an event looks like for the given problem. Use combinatorical rules on sets to model complicated expressions. 


