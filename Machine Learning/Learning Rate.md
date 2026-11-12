The change in the parameters is done by the equation:
$$ w_{k+1} = w_k - \gamma_k\nabla_w L(w_k) $$

where gamma is the learning rate.

It dictates how much to move the weights so that it goes towards the local minima fast enough to reach there but slow enough to not overshot it.