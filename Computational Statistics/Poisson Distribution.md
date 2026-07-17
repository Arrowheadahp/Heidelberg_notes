Number of cars passing in 1 hour. The number of tries are infinite (continuous time) but probability is very low for each try. This is a limit of the [[Binomial Distribution]] where $N\to\infty,\pi\to0$. For $\lambda\gets N\cdot\pi$, $$X\in \mathbb W$$$$P(X=k) = \frac{\lambda^k}{k!}e^{-\lambda}$$
Expected Values: $$\mathbb E[X] = \lambda$$ $$Var[X] = \lambda$$
### Proof of Probability Distribution:
From [[Binomial Distribution]]: $$P(X=k) = \binom{N}{k}\pi^k (1-\pi)^{N-k} $$
Taking that on average 1 success every $\lambda$ time. $E[X] = N\pi=\lambda$
Taking $N\to\infty,\pi=\lambda/N\to0$, $$\lim_{N\to\infty}\frac{\lambda^k}{N^k}\frac{N(N-1)(N-2)...(N-k+1)}{k!}(1-\lambda/N)^{N-k} $$$$\frac{\lambda^k}{N^k}\lim_{N\to\infty}(1-\frac{\lambda}{N})^{N-k}$$$$\frac{\lambda^k}{k!}e^{-\lambda}$$
