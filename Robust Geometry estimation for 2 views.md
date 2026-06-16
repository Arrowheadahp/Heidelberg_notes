This is to find geometrically the good matching points from all the matching points that we have. We plot $(x_1-x_0), (y_1-y_0)$. The outliers are ignored and the calculations are done only using inliers. To find the inliers, we define a straight line and for points nearby the value becomes 0 and points far, it becomes 1 and we minimise that function. $$ f= |ax_0 + bx_2 -1| \le t \to 0\ else\ 1$$
This is equivalent to getting the F such that $$f = |x_l^tFx_r|\le t \to0\ else\ 1$$
$$F* = \arg\min_F \sum_i f $$

### Naive approach
Enumerate all points and make lines with $(r, \theta)$. Hough transform and get the values for max. Very time consuming.

### Oracle
Oracle is a function that predicts a parameter given the minimum amount of data points (d-tuples): $$g(x_1, x_2)=f^{-1}(x_1, x_2)$$ For [[Fundamental and Essential Matrix]] calculation we only need 7 or 8 points. For [[Homography]] only 4 points are needed. So we make these sizes tuples. And instead of getting all the possible tuples, we sample randomly to get RANSAC.

### RANSAC
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

### Adaptive RANSAC
Since we do not know $\varepsilon$ from before, we assume it to be 1 and fix p very high and then adapt $\varepsilon, n$ accordingly
- $p\gets 0.999$
- $n \gets \infty$
- $\varepsilon \gets 1$
- During RANSAC:
	- Recompute $\varepsilon = \frac{outliers}{all points}$ 
	- Recompute $n=\frac{\log(1-p)}{\log(1-(1-\varepsilon)^d)}$

