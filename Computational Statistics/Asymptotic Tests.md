### Central Limit Theory

Let $x_i\in\set{1,...,n}$ iid RV with [[Variance]]>0, $\mu:=\mathbb[x_i]<\infty$
$$\lim_{n\to\infty}\frac{\bar x-\mu}{\sigma/\sqrt n}\sim N(0,1) $$
### [[Chi Squared Test]]
$\chi^2$ tests are for checking if the Residual Sum of Squares is more or less according to the degrees of freedom

### [[T-Test]]
T test is used to check if there is a significant gap between means of 2 groups.

$$\frac{\bar x-\mu}{\hat\sigma_{\bar x}}\sim t_{N-1}$$ $\hat\sigma_{\bar x}=\sigma/\sqrt n$

To check if 2 samples are from same distribution
$H_0\to\mu_1=\mu_2$
$$T=\frac{(\bar x_1-\mu_1)-(\bar x_2-\mu_2)}{\hat\sigma_{\bar x_1-\bar x_2}}\sim t_{n1+n2-2}$$