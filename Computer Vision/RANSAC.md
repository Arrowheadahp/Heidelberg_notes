
Method:
- Repeat n times
	- select d-tuple, ex: $(x_1, x_2)$ for lines but 3 points for planes etc.
	- Compute parameter(s) $y = f^{-1}(x_1, x_2)$
	- evaluate $f'(y)=\sum_i f(x_i, y)$
	- if $f'(y) \le f'(y^*)$,
		- $y^*\gets y$
		- $f'(y^*) \gets f'(y)$

Convergence:
- Let $\varepsilon$ be the probability of outliers.
- probability of inlier: $1-\varepsilon$
- probability of d-tuple being all inliers: $(1-\varepsilon)^d$
- probability of at least one of them being outlier = $1-(1-\varepsilon)^d$
- probability of getting wrong tuple all n times = $\left(1-(1-\varepsilon)^d\right)^n$
- probability of sampling the right tuple at least once = $1-\left(1-(1-\varepsilon)^d\right)^n$

This probability is very low for high n.

Since the probability of sampling a right tuple at least once is p, it is called the accuracy, $p=1-\left(1-(1-\varepsilon)^d\right)^n$.
To get accuracy p, $$ n=\frac{\log(1-p)}{\log(1-(1-\varepsilon)^d)} $$

> [!NOTE] The choice of t in f is very crucial

## Extensions of RANSAC:
### Adaptive RANSAC
Since we do not know $\varepsilon$ from before, we assume it to be 1 and fix p very high and then adapt $\varepsilon, n$ accordingly
- $p\gets 0.999$
- $n \gets \infty$
- $\varepsilon \gets 1$
- During RANSAC:
	- Recompute $\varepsilon = \frac{outliers}{all points}$ 
	- Recompute $n=\frac{\log(1-p)}{\log(1-(1-\varepsilon)^d)}$

### MSAC: M-Estimator Sample Consensus
The function becomes: $$ f(x_l, x_r, F) = \max(|x_l^tFx_r|, t)$$
Rest remains the same . 

### Randomised RANSAC
While Calculating $f'(y)=\sum_i f(x_i, y)$, instead of checking all the points, use a random selection of points. Even though good y may get rejected, because we can sample faster, and bad hypothesis of y are recognised fast, it is overall faster depending on application.

### Neural guided RANSAC
Exactly same as RANSAC but the d point tuples are being selected by a neural network instead of randomly