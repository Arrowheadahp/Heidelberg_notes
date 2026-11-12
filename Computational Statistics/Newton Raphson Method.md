This is another one of [[Iterative Estimation Methods]] similar to [[Gradient Descent]] but instead of using the first derivative, here we try to get to the derivative =0 by using the 2nd derivative. The matrix form of the second derivative is called the ==Hessian==.
$$\theta_n=\theta_{n-1}-\mathcal H^{-1}\nabla \mathcal L(\theta_{n-1}) $$

![[Pasted image 20260725143447.png]]

Calculating the $\mathcal H^{-1}$ is expensive but it converges faster for smaller dataset.