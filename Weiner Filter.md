#important 
This is the ==optimal== filter to get a regularized inverse of a convolution is obtained by minimising the squared error between predicted F and the true solution in [[Fourier Transform]] space in the case that the noise follows [[Gaussian Distribution]]
### Proof
$G=HF+N$
$N\sim  \mathcal N(0,\sigma^2)$
This is after Fourier transformation where N is Normally distributed and F is the parameters.
Let W be the [[Weiner Filter]] that transforms G into predicted F.
We find W by minimising (WG-F)^2
$$\frac{\delta}{\delta W}(W(HF+N)-F)^2\gets0$$
This results in $$W=H^{-1}\frac{1}{1+\frac{\sigma^2}{H^2P(f)}}$$
Where P(f) is the power spectrum $P(f)= F^2$
This gives good estimate with a good estimation of the power spectrum of the solution.