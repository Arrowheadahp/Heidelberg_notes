We want to find the Expected [[Squared Error]]. 
$$\mathbb E[y-\hat f_\theta(x)]$$
But in the population, there can be many samples and each sample will have its own $\hat f_\theta$.
$$\mathbb E\left[y-\hat f_\theta(x)\right]
=
\left(\mathbb E\left[\hat f_\theta(x)\right]- f(x)\right)^2
+
\mathbb E\left[\left(\hat f_\theta(x)-\mathbb E\left[\hat f_\theta(x)\right] \right)^2\right]
+
\mathbb E\left[(y-f(x) )^2\right]
$$
### Components
- **Bias** is the error in having the wrong assumptions and therefore the wrong hyperparameters/model$$\left(\mathbb E\left[\hat f_\theta(x)\right]- f_\theta(x)\right)^2$$
- **[[Variance]]** is the error in the parameters or the data present in the training sample. $$\mathbb E\left[\left(\hat f_\theta(x)-\mathbb E\left[\hat f_\theta(x)\right] \right)^2\right]$$
- **Irreducible Noise** is the noise inherent in predicting and measurement.$$\mathbb E\left[(y-f(x) )^2\right]$$
