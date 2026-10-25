This is the most used type of [[Iterative Estimation Methods]], where we try to find the global minima/maxima using iterative approaches. 
### Algorithm for GD
>We take an initial estimate for $\hat\theta$
>Repeat until $|\Delta\mathcal L(\theta)|<\varepsilon$
>>$\hat\theta_{n+1}=\hat\theta_n - \gamma\frac{\partial\mathcal L(\theta)}{\partial\theta}$

### Problems:
1. Local minima
2. Choosing Learning Rate $\gamma$

### Solutions:
1. Staring from multiple places
2. Adding Noise to GD

Most common method: ![[Stochastic Gradient Descent (SGD)]]
![[Batch Gradient Descent]]
