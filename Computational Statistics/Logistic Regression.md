Here we take a reference class let's take $l$ as the reference class
$$x_i\beta_k=\log\frac{p(c=k|x_i)}{p(c=l|x_i)}$$
$$p_i=p(c=k|x_i) = \frac{\exp(\beta_kx)}{\sum\exp(\beta x)}$$
For the 2 class case, the probabilities are $p/(1-p)$ and $1/(1-p)$
The likelihood is
$$\mathcal L=\prod p_i^{c_i}(1-p_i)^{1-c_i} $$
This is from [[Bernoulli Distribution]] when iid.
We maximise the Log Likelihood to get the betas.