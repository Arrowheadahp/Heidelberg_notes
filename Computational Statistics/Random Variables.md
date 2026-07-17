Let X be a random Variable that follows the probability distribution $P(X)=f(x)$. It is the Probability Distribution Function (PDF) and Cumulative Distribution Function is $$CDF\ F(y) := P(X\le y) = \int_{-\infty}^y f(x) dx $$
### [[Expected Values]]
Expectation Values can also be thought of as the Mean.
$$ \mathbb E[X] = \sum xP(X=x)=\int xP(X=x)dx$$

### Variance
$$ Var[X] = E[(X-E[X])^2]$$
- $Var[X] = E[X^2]-E[X]^2$
- $Var(aX+b) = a^2Var(X)$

### Covariance
Covariance is defined as 
$$ Cov[X,Y] := \mathbb E[(X-E[X])(Y-E[Y])]$$
$$ Cov[X,Y]=\sum_X\sum_YP(X,Y)(X-\mu_X)(Y-\mu_Y) $$

#### Correlation Coefficient
Here $\sigma=\sqrt{Var}$ is the Standard Deviation
$$ corr[X,Y] = \frac{Cov[X,Y]}{\sigma_X \sigma_Y}\in[-1,1]$$
#### Properties
- $Cov[X,Y] = E[XY] - E[X]E[Y]$
- $Var(X+Y) = Var(X) + Var(Y) + 2Cov[X,Y]$
- If X, Y are independent, $Cov[X,Y]=0$
- $Var[\sum X_i] = \sum Var[X_i]$ if $X_i$ are independent
- $Cov[aX+b, cx+d] = acCov[X,Y]$
- $Cov[X,Y] = Cov[Y,X]$
