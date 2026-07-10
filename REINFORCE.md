From the [[Policy Gradient Theorem]], 
$$\nabla J(\theta)\propto \sum_s\mu(s)\sum_a q_\pi(s,a)\nabla\pi(a|s,\theta) $$
$$ \sum_a q_\pi(s,a)\nabla\pi(a|s,\theta) = \mathbb E_{A\sim\pi(\cdot|S_t)}\left[q_\pi(S_t,A)\nabla\log\pi(A|S_t, \theta) \right] $$
because $\nabla\pi=\pi\cdot\log(\nabla\pi)$.
Replace by Monte Carlo Sample just like [[Monte-Carlo Methods]], $$\hat{\nabla J}\propto G_t\nabla\log\pi(A_t|S_t, \theta) $$
The above is for the undiscounted case $\gamma=1$. For the discounted case, $$J(\theta) = \mathbb E_\pi \left[\sum_{t=0}^{T-1} \gamma^tR_{t+1}| S_0=s_0 \right] = \mathbb E[G_0]=v_\pi(s_0) $$
So according to [[Gradient Descent]], $$ \theta_{t+1} = \theta_t + \alpha\nabla J(\theta) $ =\theta_t + \alpha\left( \gamma^t\cdot G_t\nabla\log\pi(A_t|S_t, \theta_t) \right)$$
$$ \theta_{t+1}-\theta_t = \alpha \gamma^t G_t\nabla\log\pi(A_t|S_t, \theta_t) $$
$G_t$ says how much the change happens and the $\nabla\log\pi(A_t|S_t, \theta_t)$ says the direction 