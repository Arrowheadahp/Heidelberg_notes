The result should only depend on the features.
It can be a, b, a.b etc.
For images or similar data we can use [[Fourier Cosine Basis]] to extract features. 
$$x_i(s) = \cos(i\pi s)$$
So for every value of $i$, we get a new feature. In Machine Learning, features with important x_i will automatically be given high weights.

### Coarse Coding
When when $x_i(s)\in\{0,1\}$, each state is either dependent on feature $i$ or not. this causes every change in weight of feature $i$ to be propagated to all the states dependent on feature $i$. 
### Polynomial
Each feature follows the following formula:$$\prod_{i=1}^ks_i^{c_i}\forall c\in\{0,1, 2,...n\} $$
So the number of possible features is $(c+1)^k$. Polynomial is global.

### Tile Encoding
#todo 
### Radial Basis Function:
This is for gradual features and is useful for very large state space.
$$x_i(s) = e^{-\frac{||s-c_i||^2}{2\sigma^2}}
$$

### Comparison:
![[Pasted image 20260626201635.png]]