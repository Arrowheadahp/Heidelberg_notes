The total loss is defined by the sum of loss function for each observation:
$$
  \mathcal{L}(\textbf{w}) = \frac{1}{N}\sum_{n=1}^{N}\textit{l}(\textbf{w}, \textbf{x}^n, \textbf{t}^n) + \textit{R}(\textbf{w})
  $$
  - x = the input 
  - w = the weights
  - t = true output
  - *R*(w) = [[Regularization]] of weights for the purpose of [[Generalization]]
  - N = number of examples

Generally, the objective of a model is to find the $\arg\min_w\mathcal L$ which is found by [[Gradient Descent]].
### ![[Squared Error]]
### ![[Cross Entropy]] 