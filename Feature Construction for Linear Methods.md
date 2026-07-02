The result should only depend on the features.
It can be a, b, a.b etc.
For images or similar data we can use [[Fourier Cosine Basis]] to extract features. 
$$x_i(s) = \cos(i\pi s)$$
So for every value of $i$, we get a new feature. In Machine Learning, features with important x_i will automatically be given high weights.

### Coarse Coding
When when $x_i(s)\in\{0,1\}$, each state is either dependent on feature i or not. this causes every change in weight of feature i to be propagated to all the states dependent on feature i. 

### Radial Basis Function:
$$x_i(s) = e^{-\frac{||s-c_i||^2}{2\sigma^2}}
$$![[Pasted image 20260626201635.png]]