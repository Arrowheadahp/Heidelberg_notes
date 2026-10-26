Rollout is a Decision time Monte Carlo Planning, similar to [[Monte-Carlo Methods]].
For each candidate action now, simulate multiple trajectories till termination according to a fixed policy. Estimate the action values by the average returns and pick the max value from the estimations.

### Algorithm
- For each action $a\in A(s)$:
	- simulate k trajectories starting with (s, a)
	- follow $\pi$
	- average the returns to estimate $$\hat q(s,a) = \frac{1}{k}\sum_i^k G_i$$
	- Choose $a\gets \arg \max_a \hat q(s,a)$

