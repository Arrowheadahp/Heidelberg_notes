Similar to [[Off-Policy MC Prediction]], $$ \rho_t^h:= \prod_{k=t}^{\min (h, T-1)}\frac{\pi(A_k|S_k)}{\mu(A_k|S_k)} $$$$ V(S) \gets V(s) + \alpha\rho_{t:t+n-1} \left(G_{t:t+n} - V(s) \right)$$
$$Q(S_t,A_t)=Q(S_t,A_t)+\alpha\rho_{t+1:t+n}(G_{t:t+n}-Q(S_t,A_t)) $$
### Control Variate
To mitigate  the issue that when $\rho=0$ the target collapses to 0 which causes variance. so the idea is to fold in a [[Control Variate]]. 
$$ G_{t:h} = \rho_t(R_{t+1} + G_{t+1:h}) + (1-\rho_t)V_{h-1}(S_t)$$
$$ V(S) \gets V(s) + \alpha\rho_{t:t+n-1} \left(G_{t:t+n} - V(s) \right)$$
This update only reduces the variance without biasing the update