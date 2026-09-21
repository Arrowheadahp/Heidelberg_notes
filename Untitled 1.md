Here's the full picture. The workspace frames "data terms" as the negative log-likelihood terms that come from the **noise model**, and they're *derived* by plugging each noise PDF into the likelihood and dropping constants.

## The three noise models and their data terms

| Noise model | PDF of the added noise | Resulting data term |
|---|---|---|
| Additive Gaussian | $p(x)=\frac{1}{\sqrt{2\pi\sigma^2}}\exp\!\big(-\frac{(x-\mu)^2}{2\sigma^2}\big)$ | $\dfrac{1}{2\sigma_m^2}\|Af-g\|_2^2$ |
| Additive exponential | $p(x)=\frac1\lambda e^{-x/\lambda},\ x\ge0$ | $\sum_i(Af-g)_i$ (an $L_1$ term) |
| Poisson | $p(k)=\frac{e^{-\mu}\mu^k}{k!}$, mean $=$ variance $=\mu$ | $\sum_i\big[(Af)_i-g_i\log(Af)_i\big]$ |

Sources: `lessons/0004-bayes-poisson-iterative.html:73-80` (Q32 table) and `all-questions-model-answers.md:267-280` (Q32/Q33).

## How each is derived

The recipe is always: write the likelihood $p(g|f)$ for the forward model $g=Af+n$, take $-\log$, and drop terms that don't depend on $f$.

**1. Additive Gaussian.** Noise enters additively: $g_i=(Af)_i+\eta_i$, $\eta_i\sim\mathcal N(0,\sigma_m^2)$, so
$$p(g|f)=\prod_i\frac{1}{\sqrt{2\pi\sigma_m^2}}\exp\!\Big(-\frac{(g_i-(Af)_i)^2}{2\sigma_m^2}\Big).$$
Taking $-\log$ kills the normalising prefactor (constant in $f$) and leaves $\frac{1}{2\sigma_m^2}\sum_i(g_i-(Af)_i)^2$. That's the standard $L_2$ data term (the same one behind Tikhonov/least squares and the Wiener filter).

**2. Additive exponential.** Here the noise is additive but exponentially distributed (one-sided, positive), giving a Laplace-like likelihood
$$p(g|f)=\prod_i \lambda^{-1}e^{-(g_i-(Af)_i)/\lambda}.$$
Then $-\log p\propto\sum_i(g_i-(Af)_i)$, i.e. $\sum_i(Af-g)_i$ up to an overall sign — an **$L_1$** data term (robust, linear, no squaring).

**3. Poisson.** The data are counts, so noise is *not* additive — it's in the mean: $g_i\sim\text{Poisson}\big((Af)_i\big)$ with $\mu_i=(Af)_i$,
$$p(g|f)=\prod_i\frac{(Af)_i^{\,g_i}e^{-(Af)_i}}{g_i!}.$$
Then
$$\log p(g|f)=\sum_i\big[g_i\log(Af)_i-(Af)_i-\log g_i!\big].$$
The $\log g_i!$ term is constant in $f$ and dropped, leaving $\sum_i\big[g_i\log(Af)_i-(Af)_i\big]$; the answer you have stored writes the equivalent form $\sum_i\big[(Af)_i-g_i\log(Af)_i\big]$ (overall sign flip, minimisation instead of maximisation).

## Why the Gaussian case gives Tikhonov, and why the means/variances matter

For Gaussian noise with a Gaussian prior, both terms are Gaussians and **their product is again Gaussian** (`lessons/0004:62-70`). Maximising the posterior gives
$$f^{MAP}=\arg\min_f\Big\{\tfrac{1}{2\sigma_m^2}\|Af-g\|^2+\tfrac{1}{2\sigma_{ap}^2}\|\tilde Df\|^2\Big\}=(A^TA+\lambda\tilde D^T\tilde D)^{-1}A^Tg,\qquad \lambda=\frac{\sigma_m^2}{\sigma_{ap}^2}.$$
So the **noise standard deviation $\sigma_m$** sets the data-term weight (the "data variance") and the **prior/apriori width $\sigma_{ap}$** sets the regularisation weight; their squared ratio is $\lambda$. This is where a covariance $\mathrm{cov}(g)$ also appears — for correlated noise the Gaussian data term becomes $\frac12(Af-g)^TC_d^{-1}(Af-g)$, and the estimation-error covariance is $\mathrm{cov}(f^{est})=M\,\mathrm{cov}(g)\,M^T$ (`all-questions-model-answers.md:218`).

## Poisson → KL divergence (the extra derivation)

The Poisson data term is exactly the Kullback–Leibler divergence. Taking the Poisson log-likelihood above, ignoring $\log g_i!$ and using conservation of total counts $\sum_i g_i=\sum_i(Af)_i$ (`lessons/0004:89-93`, Q33), it becomes
$$KL(g\|Af)=\sum_i\Big[(Af)_i-g_i+g_i\log\frac{g_i}{(Af)_i}\Big].$$
So **maximising the Poisson log-likelihood = minimising the KL divergence between the data and the forward model**. This is the objective Richardson–Lucy maximises via EM, which is why RL is the maximum-likelihood method *for the correct Poisson noise model* (`lessons/0004:113-140`).

## Where the parameters come from in the course code

There's no per-model noise generator in the workspace scripts — they all demonstrate the Gaussian case:
- `Inverse Problem Slides\l-curve.py:24-26`: `noise = np.random.normal(0, noise_level, n)` with `noise_level = 0.02`, added to the blurred signal $y_{blur}=Ax_{true}$.
- `Inverse Problem Slides\LandweberVsRichardsonLucy.py:27-31`: `noise_sigma = 0.01`, `noisy_img = blurred_img + np.random.normal(0, noise_sigma, ...)`, then `np.clip(noisy_img, 1e-6, None)` to force non-negativity so Poisson-type/RL iterations stay valid.

So the "data terms" are the model-derived objects; the actual noise draws use a chosen $\sigma$ (the Gaussian width) or a Poisson rate equal to the forward-model mean $(Af)_i$; the additivity/non-additivity and the mean–variance relation (Gaussian: fixed variance; Poisson: variance $=$ mean; exponential: one-sided positive) are what make each data term different.