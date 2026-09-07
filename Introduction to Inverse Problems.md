The idea of Inverse Problems is to get the starting parameters from the result while knowing the operation that happened to the parameters. This broad subject can be applied to many fields like physics where most of the measurements are performed on noisy data and we try to get the properties of the object from those noisy observations by using solving the Inverse Problems. 
$$ \mathcal A(f)=g $$
Here,
- $\mathcal A$ is the operation
- $f$ is the parameters
- $g$ is the result
Knowing $\mathcal A$ and $g$, ==Inverse problems== aims to find $f$ or the best estimation of it.
Getting the $g$ is called the ==Forward Problem==.
==Model Identification Problem== is to get the $\mathcal A$ given f and g.

Here we only learn about Inverse Problems for ==[[Linear System]] which is Discrete==.
$$ Af=g$$ 
#### The way to get the solution to the Inverse problem is to get the [[Pseudoinverse]].
#### When is a system a [[Linear System]]

We must be careful while calculating the inverse because if the [[Condition Number]] is high, then small noise in the measurement of $g$ can have large discrepancy in the calculation of $f$.
$$\frac{||\Delta f||}{||f||}\le cond(A)\cdot\frac{||\Delta g||}{||g||} $$
We cannot solve continuous systems directly using computers so we discretize them and then calculate the inverse.
This discretization is done by [[Newton-Cotes Method]].

#### [[Inverse Crime]]
#### [[Bias Variance Trade-off]]