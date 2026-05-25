$$Q(s, a) = \frac{\sum_{t\in\tau(s,a)}\rho_{t+1}^TG_t}{\sum_{t\in\tau(s,a)}\rho_{t+1}^T}
$$
Where the Importance Weight is calculated from [[Off-Policy MC Learning]].
$$\rho_{t_s}^T= \prod_{k=t}^{T-1}\frac{\pi(A_k|S_k)}{\mu(A_k|S_k)}$$

Limitations of Off-Policy MC:

Even though a greedy target policy can be learned, the MC updates only use trajectory parts consistent with $\pi$
If the target policy is deterministic, then [[Importance Sampling Ratio]] $$\rho_{t_s}^T= \prod_{k=t}^{T-1}\frac{\pi(A_k|S_k)}{\mu(A_k|S_k)}=0$$

> [!NOTE] Consequence
> In long episodes, MC updates receive 0 or unstable weights, so off-policy MC control can be sample-inefficient
