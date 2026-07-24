
Each of the Distributions seen above is a part of the Exponential Family of Distributions.

Conjugate Family of distributions:
$$p(\mu|X)=\frac{p(X|\mu)p(\mu)}{p(X)} $$Here $\mu$ is the parameter used in the Exponential Family equation to get the different equations. $X$ is the observed data. The Exponential Family of Distributions are Conjugate because the the ==prior== $p(\mu)$ and the ==posterior== $p(\mu|X)$ comes from the Exponential Distributions. 

The prior to [[Gaussian Distribution]] is [[Gaussian Distribution]].
The prior to [[Bernoulli Distribution]] is [[Beta Distribution]].
The prior to [[Poisson Distribution]] is [[Gamma Distribution]].

### Moment Generating Function
Let X be the Random Variable. The $E[X], E[X^2], E[X^3]$ are all moments.
$$ E[X^t]=\frac{d}{dk^t}\int f(x)e^{kx}dx $$
Here the moment generating function is: $\int f(x)e^{kx}dx$
And Differentiating it t times and putting $k=0$ gives the t-th moment. The First moment is the [[Expected Values]] and [[Variance]] can be calculated as the 2nd moment - [[Expected Values]]^2 .