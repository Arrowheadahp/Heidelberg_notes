This is a consistent and efficient way to get to the values.
Likelihood $$L=p(X|\theta)$$
Getting to the maximum likelihood, $$\hat\theta:=\arg\max_\theta p_\theta(x)$$
For iid, $p_\theta(x)=\prod_i^Np_\theta(x_i)$
the arg max is the same for log likelihood and to get to the arg max, we differentiate wrt to \theta and set it to 0
$$\frac{d}{d\theta}\sum\log p_\theta(x_i)=0 $$