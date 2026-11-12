We want to find the value that the majority agree.$$ f= |ax_0 + bx_2 -1| \le t \to 0\ else\ 1$$
This is equivalent to getting the F such that $$f = |x_l^tFx_r|\le t \to0\ else\ 1$$
We randomly sample the minimum number of points required for calculating what we want to calculate and then calculate it and do that again and again. ==The method that calculates the value with the minimum number of required points is called the Oracle==. This minimum number of points depends on what we want to calculate: F needs 7 points, H needs 4 etc.
### Algorithm
- Repeat n times
	- select d-tuple, ex: $(x_1, x_2)$ for lines but 3 points for planes etc.
	- Compute parameter(s) $y = g(x_1, x_2)$
	- evaluate $f'(y)=\sum_i f(x_i, y)$
	  this is the sum of the loss function $f$ of using the current y to on ==all the points previously sampled==.
	- if $f'(y) \le f'(y^*)$,
		- $y^*\gets y$
		- $f'(y^*) \gets f'(y)$
### Convergence:
- Let $\varepsilon$ be the probability of outliers.
- probability of inlier: $1-\varepsilon$
- probability of d-tuple being all inliers: $(1-\varepsilon)^d$
- probability of at least one of them being outlier = $1-(1-\varepsilon)^d$
- probability of getting wrong tuple all n times = $\left(1-(1-\varepsilon)^d\right)^n$
- probability of sampling the right tuple at least once = $1-\left(1-(1-\varepsilon)^d\right)^n$

This probability is very low for high n.

Since the probability of sampling a right tuple at least once is p, it is called the accuracy, $p=1-\left(1-(1-\varepsilon)^d\right)^n$.
To get accuracy p, $$ n=\frac{\log(1-p)}{\log(1-(1-\varepsilon)^d)} $$

> [!Question] Why do we use 7 points instead of 8 for calculating the [[Fundamental Matrix F]]?
> Keeping the accuracy the same decreasing d decreases the n dramatically. So we will need far fewer matching points to have the same accuracy.

> [!NOTE] We should use a good value for threshold t for the loss function $f= |ax_0 + bx_2 -1| \le t \to 0\ else\ 1$

## [[Extensions of RANSAC]]
