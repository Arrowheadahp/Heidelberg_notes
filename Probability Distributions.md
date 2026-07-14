## Discrete Probability Distributions
1. Uniform Distributions: Ex. Die$$X\in \{1, 2, ...N\},\ P(X=k)=\frac{1}{N}$$
2. [[Bernoulli Distribution]]: Coin toss$$X\in \{0,1\}$$ $$P(X=x)=\pi^x(1-\pi)^{1-x} $$
3. [[Binomial Distribution]]: Number of heads in N tosses  $$X\in\{0,1,...N\}$$ $$ P(X=k) = \binom{N}{k}\pi^k(1-\pi)^{N-k} $$
4. [[Geometric Distribution]]: Number of tries required for the first heads $$X\in \mathbb N$$$$P(X=k)=\pi(1-k)^{1-\pi}$$
5. [[Hypergeometric Distribution]]: Drawing balls without replacement. Number of successes k with n success balls among N balls with r tries.$$X\in\{0,1,...min(n,r)\}$$$$P(X=k)=\frac{\binom{n}{k}\binom{N-n}{r-k}}{\binom{N}{r}} $$
6. [[Poisson Distribution]]: Number of cars passing in 1 hour. The number of tries are infinite (continuous time) but probability is very low for each try. This is a limit of the [[Binomial Distribution]] where $N\to\infty,\pi\to0$. For $\lambda\gets N\cdot\pi$, $$X\in \mathbb W$$$$P(X=k) = \frac{\lambda^k}{k!}e^{-\lambda}$$
## Continuous Probability Distribution
$$CDF\ F(y) := P(X\le y) = \int_{-\infty}^y f(x) dx $$
For continuous probability distributions, $X\in \mathbb R$ so for any specific value of X, the probability will be 0 so we define the PDF = $f(x)=\frac{d}{dx}F(x)$ derivatives of CDF at that point.
1. [[Uniform Distribution]]: $$f(x) = \frac{1}{\theta_2-\theta_1}\ \forall x\in[\theta_2,\theta_1]$$
2. [[Gaussian Distribution]]: $$f(x) = \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}$$
3. [[Beta Distribution]]: Distribution of the probability of success after observing $\alpha$ success and $\beta$ failures. $X\in[0,1]$ $$f(x) = \frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)\Gamma(\beta)} $$
4. [[Gamma Distribution]]: The prior to the [[Poisson Distribution]]. $$f(x) = \frac{x^{\alpha-1}e^{x/\beta}}{\beta\Gamma(\alpha)} $$

## Exponential Family
Each of the Distributions seen above is a part of the Exponential Family of Distributions.

Conjugate Family of distributions:
$$p(\mu|X)=\frac{p(X|\mu)p(\mu)}{p(X)} $$Here $\mu$ is the parameter used in the Exponential Family equation to get the different equations. $X$ is the observed data. The Exponential Family of Distributions are Conjugate because the the prior $p(\mu)$ and the posterior $p(\mu|X)$ comes from the Exponential Distributions. 

The prior to [[Gaussian Distribution]] is [[Gaussian Distribution]].
The prior to [[Bernoulli Distribution]] is [[Beta Distribution]].
The prior to [[Poisson Distribution]] is [[Gamma Distribution]].

### Moment Generating Function
Let X be the Random Variable. The $E[X], E[X^2], E[X^3]$ are all moments.
$$ E[X^t]=\frac{d}{dk^t}\int f(x)e^{kx}dx $$
Here the moment generating function is: $\int f(x)e^{kx}dx$
And Differentiating it t times Ives the t-th moment. The First moment is the mean and the Second moment is the Variance.

### Multivariate Probability Distributions
1. Multicategoric Distributions: Generalization of [[Bernoulli Distribution]]
2. Multinomial Distribution: Generalization of [[Binomial Distribution]]
3. Multivariate Normal Distribution: Generalization of [[Gaussian Distribution]]
#todo 