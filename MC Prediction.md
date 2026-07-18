[[State Value]] is calculated as $$v_\pi(s) = \mathbb{E}_\pi[G_t|S_t=s] = \frac{1}{n}\sum_{i=1}^n G_i(s)$$
- Generate as many episodes following [[Policy]] $\pi$.
- For each state s, average the [[Return]].

[[Return]] from time t: $$G_{t_i}:=\sum_{k=0}^{T-t_i-1} \gamma^k R_{t_i+k+1}$$
There are 2 ways to update the $v_\pi(s)$:
1. [[First Visit Monte Carlo]]
   final for n episodes where s was visited: $$v_\pi(s) = \frac{1}{n}\sum_{i=1}^n G_1(s)$$
2. [[Every Visit Monte-Carlo]]
   final for n episodes where s was visited, for $k_n$ visits in each episode: $$v_\pi(s) = \frac{1}{n}\sum_{i=1}^n \sum_j^{k_n} G_j(s)$$
### Algorithm:

- Initialize V(s) with arbitrary values.
- For each episode:
	- generate episode with policy $\pi$.
	- for each state s that appears is the episode:
		- Let G be the return after first visit to s
		- Append G to Returns\[s\]
		- $V(s)\gets (Returns(s))$
		$$ V(s) \gets V(s) + \frac{1}{N(s)} \left(G - V(s) \right)$$
This update can also be done using [[Batch Updating]]