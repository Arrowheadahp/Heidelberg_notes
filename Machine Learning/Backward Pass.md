We calculate the gradient 
$$\nabla_w \it L(w, x, t)$$

Going over all the observation for each step is too expensive 
So the gradient is calculated for a subset (mini-batch)
This is called [[Stochastic Gradient Descent (SGD)]]

Each epoch, the training examples are shuffled. One epoch is single pass for all the examples
