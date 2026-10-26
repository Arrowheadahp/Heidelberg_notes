The motivation is to generate a stationary probability distribution from an initial sequence of samples to generate another sequence of samples so that after finite iterations, it converges to stationary probability distribution. This algorithm solves the [[MCMC]] by making a transition matrix 
The condition that it converges is $p(i)p(i\to j)=p(j)p(j\to i)$

We split the transition into 2 steps;
1. make a proposal of j with $q(j|i)$
2. accept the proposal with probability $\alpha(j|i)$
Therefore $p(i\to j)=q(j|i)\alpha(j|i)$
From the condition we get the result $$\frac{\alpha(j|i)}{\alpha(i|j)}=\frac{p(j)q(j|i)}{p(i)q(i|j)} $$
this is fulfilled by $$\alpha(j|i)= \min(1, \frac{p(j)q(j|i)}{p(i)q(i|j)})$$
after a lot of iterations, we get the answer distribution by sampling from the last iteration

> [!NOTE] All we need to get the probability distribution is just the ratio of 2 samples for each sample. 
> this will work with any non zero proposal probability, we we can use symmetric probability to cancel them out.$$\alpha(j|i)=\min(1, \frac{p(j)}{p(i)})$$

