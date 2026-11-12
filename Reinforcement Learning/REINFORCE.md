#tobeunderstood 
From the [[Policy Gradient Theorem]], 
$$\nabla J(\theta)\propto \sum_s\mu(s)\sum_a q_\pi(s,a)\nabla\pi(a|s,\theta) $$
$$ \sum_a q_\pi(s,a)\nabla\pi(a|s,\theta) = \mathbb E_{A\sim\pi(\cdot|S_t)}\left[q_\pi(S_t,A)\nabla\log\pi(A|S_t, \theta) \right] $$
because $\nabla\pi=\pi\cdot\log(\nabla\pi)$.
Replace by Monte Carlo Sample just like [[Monte-Carlo Methods]], $$\hat{\nabla J}\propto G_t\nabla\log\pi(A_t|S_t, \theta) $$
The above is for the undiscounted case $\gamma=1$. For the discounted case, $$J(\theta) = \mathbb E_\pi \left[\sum_{t=0}^{T-1} \gamma^tR_{t+1}| S_0=s_0 \right] = \mathbb E[G_0]=v_\pi(s_0) $$
So according to [[Gradient Descent]], $$ \theta_{t+1} = \theta_t + \alpha\nabla J(\theta) $$
$$ \theta_{t+1}-\theta_t = \alpha \gamma^t G_t\nabla\log\pi(A_t|S_t, \theta_t) $$

> [!Question] Should I make the sampled action more likely or less next time?
> $G_t$ says increase or decrease and by how much the change happens and the $\nabla\log\pi(A_t|S_t, \theta_t)$ says the direction in $\theta$ that increases $\pi(A_t|S_t)$. 

### Pseudocode
- Input: Differentiable policy $\pi$
- Parameter: step size $\alpha>0$
- Initialize $\theta\in\mathbb R^d$
- Loop Forever:
	- Generate episode
	- for each step t:
		- $G\gets\sum_{k=t+1}^T \gamma^{k-t-1} R_k$
		- $\theta\gets\theta+\alpha\gamma^tG\nabla\log\pi(A_t|S_t, \theta)$

### Soft-Max Linear Policy:
$$\pi(s,\theta)= \frac{e^{\theta^Tx(s,a)}}{\sum_{b=1}^{k}e^{\theta^Tx(s,b)}} $$
$$ \log \pi(s,\theta) = \theta^Tx(s,a) - \log \sum_{b=1}^{k}e^{\theta^Tx(s,b)}$$
$$\nabla\log\pi(s,\theta) = x(s,a) - \sum_b\pi(b|s,\theta)x(s,b)$$
### Properties of REINFORCE
> [!NOTE] REINFORCE signature behavior
> Works but $\alpha$ sensitive.

- **Unbiased** estimator of policy gradient direction up to theorem's constant of proportionality.
- **Converges** to a local optimum of J under standard stochastic approximation conditions.
- $G_t$ has high **Variance** so learning is slow.

> [!NOTE] Variance being the bottleneck 
> The parameter $\nabla\theta$ depends on entire future trajectory. To solve this, Baseline and Bootstrapping is introduced.

