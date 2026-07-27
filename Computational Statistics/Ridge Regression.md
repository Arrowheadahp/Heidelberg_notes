This is a kind of [[Regularization]]. This is used to make the $\beta$ values completely 0 for some features.
The [[Loss Function]]  of [[Squared Error]] becomes:
 $$\mathcal L(\beta) = (y-\hat y)^T(y-\hat y) + \lambda\beta^T\beta$$
This comes to $$\hat\beta=(X^TX+\lambda I)^{-1}X^Ty $$

The Lasso Regression can be reformulated as a constrained optimization problem where $$\lambda\sum_{j=1}^p\beta_j^2\le t$$