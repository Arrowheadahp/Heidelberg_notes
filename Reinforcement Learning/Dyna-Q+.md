Variant of [[Dyna-Q]] with a exploration bonus build in. Similar to [[Upper Confidence Bounds Approach]] but instead of uncertainty, this depends on for how many steps a particular a has not been taken and adds the bonus to the reward. This is good method in [[Non-Stationary Reinforcement Learning]].

- This model rechecks parts of the model that it has neglected
- It can detect environmental changes
- It can detect if the model has become stale or not.
### Algorithm

- Maintain
	- [[State Value Function]] `Q(S, A)`
	- Model `M[S, A] = (R, S')`
	- Set of previously seen state action pairs
	- $\tau(s,a)$: Number of steps since (s,a) has been tried
- Per real state:
	- Choose a from s by $\varepsilon$-greedy on `Q`
	- execute a, observe r, s'
	- Direct RL update [[Q-Learning]]: $$Q(S_t, A_t) \gets Q(S_t, A_t)+\alpha( R_{t+1}+\gamma \max_a Q (S_{t+1}, a) - Q(S_t, A_t))$$
	- Store model entry $M[s,a] \gets (r, s')$
	- Repeat n times:
		- sample old $sp, ap$
		- get $rp, s'p \gets M[sp, ap]$
		- $rp \gets rp +\kappa \sqrt{\tau(s,a)}$
		- update `Q(S,A)` using [[Q-Learning]]
		- update $\tau(s,a)$
	- $s\gets s'$
