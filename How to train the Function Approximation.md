### Prediction Objective
> [!Question] When we cannot be right everywhere, how should we compromise?
> We craft a loss function is such a way that we give importance to states we visit on-policy. This loss function is called the [[Prediction Objective]].

So we weigh the states according to probability of visiting state s under policy $\pi$ and this probability is $\mu(s)$. 
So the [[Prediction Objective]] with Mean Squared Error becomes $$\bar{VE}(w) = \sum_s \mu(s) \left(v_\pi(s)- \hat v(s,w)\right )^2 $$
In a continuous task: $\mu$ is the long run fraction of time spent on state s.

### SGD on [[Prediction Objective]]:
Using [[Stochastic Gradient Descent (SGD)]] to reduce the [[Prediction Objective]]:
$$w_{t+1} = w_t + \alpha \nabla_w VE(w) = w_t + \alpha [v_\pi(S_t, w_t)-\hat v(S_t, w_t)]\nabla_w \hat v(S_t, w_t)
$$
$\nabla_w \hat v(S_t, w_t)$ comes from the Machine Learning Algorithm. But since we do not know the $v_\pi(S_t)$, we use the [[Target Update]] for the value function $U_t$ $$w_{t+1} = w_t + \alpha \nabla_w VE(w) = w_t + \alpha [U_t-\hat v(S_t, w_t)]\nabla_w \hat v(S_t, w_t)
$$

This converges only when the $\mathbb E [U_t]=v_\pi$. But bootstrapping v is generally biased and reducing $\alpha$ won't work for non-stationary problems.