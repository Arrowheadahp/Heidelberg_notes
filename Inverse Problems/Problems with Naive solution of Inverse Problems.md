The OTF can be 0 or very small values for large frequencies. 
After the PSF operation, there can be some noise added. $$ g=PSF\otimes f+\varepsilon$$
$$G=OTF\cdot F+E$$
$$F = \frac{G-E}{OTF}$$
Using the naive solution of $F=\frac{G}{OTF}$ will not work. And we do not know the E. 

There will always be a requency over which the noise will have more than the signal because the noise is invariant to the frequency. Meaning mathematically, 
There exists a frequency $\omega_0$ so that $\forall \omega>\omega_0$, $$F(\omega)<<E(\omega)$$ $$\therefore \frac{F(\omega)}{OTF(\omega)}<<\frac{E(\omega)}{OTF(\omega)}$$
This means that noise will get blown up in after inverse. To compensate for the noise we use a [[Regularization]] constant that gets added to the OTF before dividing.
$$\hat F = \frac{G}{OTF+s^2}$$

There can be other kinds of noise, like Poisson noise (noise that follows [[Poisson Distribution]]) but because of [[Central Limit Theory]], overall noise distribution converges to [[Gaussian Distribution]]. So the equation becomes $$g=Af+\varepsilon, \varepsilon\sim\mathcal N(\mu,\sigma^2)$$
