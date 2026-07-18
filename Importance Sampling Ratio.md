The [[Importance Sampling Ratio]] $\rho$ can be calculated using policies alone and does not require model to be computed.

$$\frac{\pi(x)}{\mu(x)} = \frac{target\ prob}{behaviour\ prob} = \frac{Pr_\pi(trajectory)}{Pr_\mu(trajectory)}$$
$$\frac{Pr_\pi(trajectory)}{Pr_\mu(trajectory)} = \frac{\prod_{k=t}^{T-1}\pi(A_k|S_k)P(S_{k+1}|S_k, A_k)}{\prod_{k=t}^{T-1}\mu(A_k|S_k)P(S_{k+1}|S_k, A_k)} = \prod_{k=t}^{T-1}\frac{\pi(A_k|S_k)}{\mu(A_k|S_k)} =: \rho_t^T
$$

Target policy value: $$ v_\pi(s) = \mathbb{E}_\pi[G_t|S_t=s] = \mathbb{E}_\mu[\rho _t^T G_t|S_t=s] $$

Because the [[Importance Sampling Ratio]] gets very unstable, there are 2 ways of calculating the [[State Value]] during iterations:
1. Ordinary Importance Sampling which is unbiased but high variance:$$ V(s) = \frac{1}{|\tau(s)|}\sum_{t\in\tau(s)}\rho_t^TG_t
$$
2. Weighted Importance Sampling with small bias but much smaller variance:$$V(s) = \frac{\sum_{t\in\tau(s)}\rho_t^TG_t}{\sum_{t\in\tau(s)}\rho_t^T}
$$
Where $|\tau(s)|$ represents the number of times state s has been visited.
