### Adaptive RANSAC
Since we do not know $\varepsilon$ from before, we assume it to be 1 and fix p very high and then adapt $\varepsilon, n$ accordingly
- $p\gets 0.999$
- $n \gets \infty$
- $\varepsilon \gets 1$
- During RANSAC:
	- Recompute $\varepsilon = \frac{outliers}{all points}$ 
	- Recompute $n=\frac{\log(1-p)}{\log(1-(1-\varepsilon)^d)}$

### MSAC: M-Estimator Sample Consensus
The function becomes: $$ f(x_l, x_r, F) = \min(|x_l^tFx_r|, t)$$
Rest remains the same . 

### Randomised RANSAC
While Calculating $f'(y)=\sum_i f(x_i, y)$, instead of checking all the points, use a random selection of points. Even though good y may get rejected, because we can sample faster, and bad hypothesis of y are recognised fast, it is overall faster depending on application.

### Neural guided RANSAC
Exactly same as RANSAC but the d point tuples are being selected by a neural network instead of randomly