
The loss function is defined by:
$$
  \textit{L}(\textbf{w}) = \frac{1}{N}\sum_{n=1}^{N}\textit{l}(\textbf{w}, \textbf{x}^n, \textbf{t}^n) + \textit{R}(\textbf{w})
  $$
  - x = the input 
  - w = the weights
  - t = true output
  - *R*(w) = [[Regularization]] of weights
  - N = number of examples


Cross Entropy is the most used loss function for classification ^cross

$$
\textit{l}(\textbf{x, t, w}) = -\sum_{j}t_j log(p(c_j|x))
$$
where $$ p(c_j=1|x) = \frac{e^{y_j}}{\sum_{k=1}^{C}e^{y_k}} $$
