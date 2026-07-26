### Support Vector Machines
Linear Classifier that ==maximises the minimum separation== between 2 classes. It can also use kernel functions to change the basis and solve the maximum margin for overlapping classifications as well.
Principles:
1. Maximum Margin
2. Basis Expansion
3. Kernel Functions

The boundary given by $\beta$ is calculated such that
$$\hat\beta= \arg\max_\beta\left[\min_i\frac{c_i(x_i\beta)}{||\beta||} \right]$$where $c_i(x_i\beta)=1$ for closest point and higher for other points
### Basis Expansion
#### Polynomial
Each feature follows the following formula:$$\prod_{i=1}^ks_i^{c_i}\forall c\in\{0,1, 2,...n\} $$
So the number of possible features is $(c+1)^k$. Polynomial is global.


#### Radial Basis Function:
This is for gradual features and is useful for very large state space.
$$x_i(s) = e^{-\frac{||s-c_i||^2}{2\sigma^2}}
$$
