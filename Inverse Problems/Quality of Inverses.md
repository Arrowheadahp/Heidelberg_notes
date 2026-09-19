[[Data Resolution Matrix (N)]] and [[Model Resolution Matrix (R)]] are perfect when they are diagonal. So we can get a measure of how good the $A^{PI}$ is by the spread of $N$.

Spread(B) is the 2-norm of ($B-I$) = $||B- \mathbb I||^2_2$

We use this spread function to calculate the [[Loss Function]] $J$ and then calculate  $\arg\min_{A^{-1}}J$ by $$\frac{\delta J}{\delta A^{-1}}\gets0$$
### Minimize the spread of N
$$\frac{\delta ||AA^{PI}-\delta||^2_2}{\delta A^{-1}}=0$$$$\frac{\partial (AA^{PI}-\delta)^T(AA^{PI}-\delta)}{\partial A^{PI}}=0$$ $$A^{PI}=(A^TA)^{-1}A^T$$
The general case is to minimize $$\Gamma=\alpha_1spread(N)+\alpha_2spread(R) +\alpha_3size(cov(f))$$
This comes down to the ==![[Sylvester Equation]]== 
Here the alphas are weighted accordingly
1. Data resolution: The reconstructed model tries to reproduce the data perfectly
2. Model Resolution: If true model has sharp feature, the resolution should also have it
3. Distance weighted spread: ghosting of localized features

This gives the [[Backus Gilbert Solution]]

| Feature        | [[Tikhonov Regularization]]                    | [[Backus Gilbert Solution]]         |
| -------------- | ---------------------------------------------- | ----------------------------------- |
| Goal           | minimize $\left ((Af-g)^2+\lambda D(f)\right)$ | minimize spread                     |
| Kernels        | often have sidelobe artifacts                  | specifically suppresses sidelobes   |
| Best used when | high SNR: Signal to Noise Ratio                | Spacial location is primary concern |

### Examples of solutions:
![[Damped Least Squares]]
![[Damped Minimum Length]]