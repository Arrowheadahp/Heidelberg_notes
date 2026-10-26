Here 
- behaviour policy $\mu$ does the [[Exploration]] and 
- the target policy $\pi$ does the [[exploitation]]. This might be deterministic.

>[!Note] If $\pi(s)=a$ then $\mu(s,a)>0$. Otherwise target policy experience will not be experienced.

$$ \mathbb E_\pi [f(X)] = \sum_x \pi(x)f(x) = \sum_x \mu(x)\frac{\pi(x)}{\mu(x)}f(x) = \mathbb E_\mu \left[\frac{\pi(x)}{\mu(x)}f(x) \right]
$$
Sample [[Return]] coming from $\mu$ can have the same expectation as coming from $\pi$ when multiplied by $$\frac{\pi(x)}{\mu(x)} = \frac{target\ prob}{behaviour\ prob} = \frac{Pr_\pi(trajectory)}{Pr_\mu(trajectory)}$$
$$\frac{Pr_\pi(trajectory)}{Pr_\mu(trajectory)} = \frac{\prod_{k=t}^{T-1}\pi(A_k|S_k)P(S_{k+1}|S_k, A_k)}{\prod_{k=t}^{T-1}\mu(A_k|S_k)P(S_{k+1}|S_k, A_k)} = \prod_{k=t}^{T-1}\frac{\pi(A_k|S_k)}{\mu(A_k|S_k)} =: \rho_t^T
$$
The [[Importance Sampling Ratio]] $\rho$ is being calculated using policies alone and does not require model to be computed.
## Algorithm:
Incremental Weighted Importance Sampling for First Visit Off-Policy MP Prediction
- Initiate V(s), C(s)
- For each episode:
	- Compute [[Return]] $G_t$  for all t.
	- for each state s compute $t_s$ be the first time s is being visited:
		- let $t_s = \min_t(S_t=s)$
		- Compute the Importance Weight $$\rho_{t_s}^T= \prod_{k=t}^{T-1}\frac{\pi(A_k|S_k)}{\mu(A_k|S_k)}$$
	- update $C(s) \gets C(s) + \rho_{t_s}^T$
	- update V(S)$$ V(S) \gets V(s) + \frac{\rho_{t_s}^T}{C(s)} \left(G_{t_s} - V(s) \right)$$
Each state is updated once per episode, using first return and its first-visit importance weight