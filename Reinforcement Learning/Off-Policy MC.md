Instead of same policy generating data and being improved in [[On-Policy MC Control]], Here 
- behaviour policy $\mu$ does the [[Exploration]] and 
- the target policy $\pi$ does the [[exploitation]]. This might be deterministic.


- The [[State Value]] $v_\pi$ is calculated by the [[Off-Policy MC Prediction]]$$V(s) = \frac{\sum_{t\in\tau(s)}\rho_t^TG_t}{\sum_{t\in\tau(s)}\rho_t^T}
$$
- The [[Action Value]] $q_\pi$ is calculated by the [[Off-Policy MC Control]].$$Q(s, a) = \frac{\sum_{t\in\tau(s,a)}\rho_{t+1}^TG_t}{\sum_{t\in\tau(s,a)}\rho_{t+1}^T}
$$