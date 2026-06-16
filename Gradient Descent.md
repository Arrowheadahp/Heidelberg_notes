This is a type of [[Iterative Estimation Methods]], where we try to find the global minima/maxima using iterative approaches. 

1. Initialize weights w0
2. Iterate k times
	1. for each example n
		1. [[Forward Pass]] to compute **h, y, ==p(c)==**
		2. [[Backward Pass]] to compute the gradients $$\nabla_w \it L(w, x, t)$$
	2. Average gradient over all examples 
	   $$ \nabla_w\textit{L}(w_k) = \frac{1}{N} \sum_{n=1}^{N}\nabla_w\textit{l}(w, x^n, t^n) + \nabla_w\textit{R}(w) $$
	   *R* is for weight [[Regularization]].
	3. average gradient descent step
	   $$ w_{k+1} = w_k - \gamma_k\nabla_w L(w_k) $$
gamma is the [[Learning Rate]].