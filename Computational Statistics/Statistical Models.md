Populations is the real probability distribution from which samples are taken. When we collect data, we only get the sample, but the sample may not represent the population well.

What we can do with Statistical models:
1. Hypothesis Testing
2. Prediction

### Random sample:
$$ X=\{x_1, x_2 ... x_n\}=\{x_i\}$$
$$p(x) = \frac{1}{\binom{K}{N}}$$

### Statistics

Sample mean: $\bar x:=\frac{1}{N}\sum x_i$
Sample Variance: $\sigma^2:=\frac{1}{N-1}\sum (x_i-\bar x)^2$

Law of large numbers(weak) states that when N is large enough, the sample statistics is infinitely close to the population statistics.
$$\lim_{N\to\infty}P(|\bar \theta-\theta|<\varepsilon)=1\ \forall\varepsilon>0 $$

### Statistical Inference
$D = \{y_i,x_i\},i\in\{1...N\}$
where $y_i$ is the $i$-th observed value and $x_i$ is the observed predictors.

For a linear model: $$y_i=\beta_0+\sum_{j=1}^p\beta_jx_{ij}+\varepsilon_i $$
where $\varepsilon\sim N(0,\sigma^2)$.
$\beta :=(\beta_0...\beta_p)^T$
$X={1,x_1,x_2...x_p}$
$$y=X\beta+\varepsilon$$

