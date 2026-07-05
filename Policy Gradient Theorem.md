Policy Gradient Theorem states that for any differentiable policy $\pi(a|s,\theta)$,$$\nabla J(\theta)\propto \sum_s\mu(s)\sum_a q_\pi(s,a)\nabla\pi(a|s,\theta) $$
Where J is the expected return at the starting state.$$J(\theta) \approx v_\pi(S_0)$$
### Proof
where $v_\pi(s)=\sum_a\pi(a|s)q_\pi(s,a)$ from [[Bellman Equations]]
And  $$\nabla J(\theta)= \nabla v_\pi(S_0)$$
$$\nabla v_\pi(s) = \sum_a \left\{\nabla\pi(a|s)q_\pi(s,a) + \pi(a|s)\nabla q_\pi(s,a) \right\} $$
From [[Bellman Equations]],$$
q_\pi(s,a) = \sum_{s', r} \left(p(s',r|s,a)\left[r+\gamma v_\pi (s')\right] \right)
$$
$$\therefore\nabla q(s,a) = \gamma \sum_{s'} p(s'|s,a)\nabla v_\pi(s') $$

So the equation comes to $$\nabla v_\pi(s) = \sum_a\nabla\pi(a|s)q_\pi(s,a) + \sum_a\left(\pi(s,a)\sum_{s'}p(s'|s,a)\nabla v_\pi(s')\right) $$
We define 
- $\varphi(s) \gets \sum_a\nabla\pi(a|s)q_\pi(s,a)$
- $P_\pi(s'| s)\gets\sum_a\pi(a|s)p(s'|s,a)$
So the equation becomes $$\nabla v_\pi(s)=\varphi(s)+\gamma\sum_{s'}P_\pi(s'|s)\nabla v_\pi(s') $$
$$\nabla v_\pi(s) = \sum_{t=0}^{T-1}\left(\gamma^t\sum_uPr_\pi(s\to u\ in\ t\ steps)\varphi(u) + \gamma^T\sum_uPr_\pi(s\to u,T)\nabla v_\pi(u) \right)$$
At $T=\infty$,
$$\nabla v_\pi(s)=\sum_u\left(\sum_t\gamma^tPr(s\to u,t)\right)\varphi(u) $$
When putting $s\gets s_0$ and defining $C = \sum_u\left(\sum_t\gamma^tPr(s\to u,t)\right)$ and $\mu(u) = \frac{\sum_t\gamma^tPr(s\to u,t)}{C}$, and putting $\varphi$ value,

$$\nabla J(\theta)=\nabla v_\pi(s_0)= C\sum_u\mu(u)\sum_a q_\pi(u,a)\nabla\pi(a|u) $$
$$\therefore\nabla J(\theta)\propto \sum_s\mu(s)\sum_a q_\pi(s,a)\nabla\pi(a|s,\theta) $$


