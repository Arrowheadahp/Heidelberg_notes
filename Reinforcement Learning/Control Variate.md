#tobeunderstood 
To mitigate  the issue that when $\rho=0$ the target collapses to 0 which causes variance. so the idea is to fold in a Control Variate. 
$$ G_{t:h} = \rho_t(R_{t+1} + G_{t+1:h}) + (1-\rho_t)V_{h-1}(S_t)$$
$$ V(S) \gets V(s) + \alpha\rho_{t:t+n-1} \left(G_{t:t+n} - V(s) \right)$$
This update only reduces the variance without biasing the update

The [[N-Step Expected SARSA]] flavoured Off Policy return:
$$G_{t:h}^{CV} = R_{t+1} + \gamma\left(V_{h-1}(S_{t+1}) + \rho_{t+1}\left[G_{t+1:h}^{CV} - Q_{h-1}(S_{t+1}, A_{t+1})\right]\right)
$$$$V_{h-1}(S_{t+1}) = \sum_a\pi(a|S_{t+1})Q_{h-1}(S_{t+1}, a)$$
- The term $G_{t+1:h}^{CV} - Q_{h-1}(S_{t+1}, A_{t+1})$ is the surprise beyond current estimate
- The default expected value is: $V_{h-1}(S_{t+1})$
- $\rho_{t+1}$ corrects only sampled deviations from current estimate value
- When $\rho_{t+1}=0$, target falls back to  $V_{h-1}(S_{t+1})$