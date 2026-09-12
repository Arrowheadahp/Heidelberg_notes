Objective:
1. Linear inverse problems that are characterized by convolution ([[Toeplitz Matrix]]), a naive solution increases the noise.
2. How to optimally reconstruct the signal and using [[Weiner Filter]] and the definition of optimality.
3. [[Tikhonov Regularization]]
The [[Problems with Naive solution of Inverse Problems]] is that the small errors in the measurement of g causes lot of inaccuracies. 
The solution is [[Regularization]]. 
$$\hat F = \frac{G}{OTF+s^2}$$
Changing the value of $s$ changes the regularization amount. For some values of $s$ the Image improves.
### [[Weiner Filter]]
This is the ==optimal== filter to get a regularized inverse of a convolution that is obtained by minimising the squared error between predicted F and the true solution

### [[Simplified Discussions]]
Another way of [[Regularization]] is to change the singular values of D to $s_{ii}\gets s^2\forall s_{ii}<\delta<<1$.

### [[Tikhonov Regularization]]
$$f^*=\arg\min_f\left ((Af-g)^2+\lambda D(f)\right) $$
### [[p-Norms]]
There are many norms that can be used just like L2 norm and L1 norm
### [[Non-Linear Regularization]]

For constraining the values of f to be only positive, we can use methods like the [[Lagrange Multiplier]] or [[POCS]]

### [[Underdetermined Problems]]

## [[Classification of Models]]
