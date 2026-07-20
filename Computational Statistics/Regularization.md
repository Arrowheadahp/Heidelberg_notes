The loss function is   $$
  \textit{L}(\textbf{w}) = \frac{1}{N}\sum_{n=1}^{N}\textit{l}(\textbf{w}, \textbf{x}^n, \textbf{t}^n) + \textit{R}(\textbf{w})
  $$
*R* is the regularizer.
This makes so that with small amount of data the weights do not overfit, so it works as a smoothener

3 most used regularization:
1. L1 regularization (Lasso)
2. L2 regularization (Ridge)
3. Elastic Net regularization (Combination of Ridge and Lasso)