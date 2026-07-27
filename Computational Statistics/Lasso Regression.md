This is a kind of [[Regularization]] mainly used for [[GLM (General Linear Model)]]. This is used to make the $\beta$ values completely 0 for some features.
The [[Loss Function]]  of [[Squared Error]]becomes:
 $$\mathcal L(\beta) = \frac{1}{N}\sum_{i=1}^N(y_i-\hat y_i)^2 + \lambda\sum_{j=1}^p|\beta_j|$$
This comes to $$\hat\beta=\frac{\sum x_iy_i}{\sum x_i^2}-\frac{\lambda d}{2\sum x_i^2} $$

The Lasso Regression can be reformulated as a constrained optimization problem where $$\lambda\sum_{j=1}^p|\beta_j|\le t$$