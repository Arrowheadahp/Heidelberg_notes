This is REINFORCE with a specific Baseline. 
REINFORCE with a normal baseline is:
$$ \theta_{t+1}=\theta_t + \alpha \gamma^t (G_t \color{yellow}{-b(S_t)})\nabla\log\pi(A_t|S_t, \theta_t) $$
When we use $b(S_t) = \hat v(s,w)$, then $\delta = G_t - \hat v(S_t,w)$ becomes the advantage of the chosen action over other actions available at state $S_t$. It signifies if the action was better or worse than expected.
### Pseudocode
- Input: Differentiable policy $\pi$ and value function $\hat v(s,w)$
- Parameter: step size $\alpha_\theta, \alpha_w>0$
- Initialize $\theta,w\in\mathbb R^d$
- Loop Forever:
	- Generate episode
	- for each step t:
		- $G\gets\sum_{k=t+1}^T \gamma^{k-t-1} R_k$
		- ==advantage== $\delta \gets G-\hat v(S_t,w)$
		- $\theta\gets\theta+\alpha_\theta\gamma^t\delta\nabla\log\pi(A_t|S_t, \theta)$
		- $w \gets w+\alpha_w\delta\nabla\hat v(S_t,w)$

### Properties
- Baseline is usually a learned value function $b(s) = \hat v(s,w)$
- A common update is Monte-Carlo regression $w \gets w+\alpha_w\delta\nabla\hat v(S_t,w)$
- $\delta = G_t - \hat v(S_t,w)$ signifies if the action was better or worse than expected.
- This does not turn the the method into value based method. ==the policy is still the actor==, the value only helps in the update.
