The total loss is defined by the sum of loss function for each observation:
$$
  \textit{L}(\textbf{w}) = \frac{1}{N}\sum_{n=1}^{N}\textit{l}(\textbf{w}, \textbf{x}^n, \textbf{t}^n) + \textit{R}(\textbf{w})
  $$
  - x = the input 
  - w = the weights
  - t = true output
  - *R*(w) = [[Regularization]] of weights
  - N = number of examples

### [[Squared Error]]
### [[Cross Entropy]] 

[[Precision-Recall Curve]] can also be used to quantify how good a model is in tasks like labelling.