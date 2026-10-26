## Markov Chain Monte Carlo
The motivation is to get to the posterior distribution of [[Bayes Theorem]] without the evidence because getting the evidence is hard. 
$$p(f|g)\propto p(g|f)\cdot p(f)$$
For that, we use the [[Markov Chains]].
![[Markov Property]]

- we generate an initial sequence of samples form an initial probability distribution.
- we sample from the next sequence from the previous sequence of samples.
For sampling the next sequence we need the ==transition matrix==. This is the $P_{ij}$ which stores the probability of going from ith state to jth state. This is similar to [[What is a Finite Markov Decision Process]]. 

But we don't have the Transition matrix. so the solution is [[Metropolis Hastings Algorithm]]
