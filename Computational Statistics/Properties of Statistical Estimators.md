#### Properties of a good statistics
Here $\theta$ is the statistics and any variable with a hat is the predicted value

1. $\mathbb E[\hat\theta]=\theta+c$
   Here c is the bias and so when c=0, the estimator is unbiased.
2. Consistency
   $$\lim_{N\to\infty}P(|\bar \theta-\theta|<\varepsilon)=1\ \forall\varepsilon>0 $$
3. Sampling distribution:  This is the distribution of a specific sample statistic.
4. **Standard Error** $$SE_\hat\theta (N):=\sqrt{\mathbb E\left[\left(\hat\theta-\mathbb E\left[\hat\theta\right]\right)^2\right]} $$ This is the variance of the sample statistic. Meaning it calculates how much the statistic varies from the average statistic that we could have calculated with different sample clusters.
5. Sufficient Statistic $T(x)$ such that $p(x|T,\theta) = p(x|T)$. It is the minimally sufficient set of statistics or parameters to describe the random variable.
6. Efficiency$:=\frac{SE^2_\theta}{SE^2_\hat\theta}\in[0,1]$

