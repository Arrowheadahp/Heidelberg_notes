#important 
### Approach
$$g=Af+\varepsilon$$
Tikhonov's idea is to formulate the problem as
$$f^*=\arg\min_f(Af-g)^2$$This is minimising the ==fidelity==.
Solving this is similar to [[Inference for linear regression]] which gives the solution for [[Pseudoinverse]].$$ f = (A^TA)^{-1}A^Tg=A^{PI}g$$
### Regularization
For getting more robust values the process of [[Regularization]] that ikhonov introduced is $$f^*=\arg\min_f\left ((Af-g)^2+\lambda D(f)\right) $$
Where 
- $\lambda$ is the Regularization parameter (scalar positive)
- $D(f)$ is the Regularization function which only has positive values (can be identity matrix as well)

#### When D(f) = (Df)^T (Df)
This becomes similar to [[Ridge Regression]] where $D=I$. 
$$f_\lambda=(A^TA+\lambda D^TD)A^Tg=A^{PI}_\lambda g$$
Choice of $\lambda$ comes down to [[Bias Variance Trade-off]]

### Limits of [[Tikhonov Regularization]]
1. Deblurring can never be perfect unless $\lambda=0$
2. Due to limited frequency bandwidth, there will be artifacts near sharp objects
We cannot remove these limitations no matter what D we choose.