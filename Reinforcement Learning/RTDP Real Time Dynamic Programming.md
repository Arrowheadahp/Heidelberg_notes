[[On-Policy]] trajectory-sampling version of value iteration like [[Value Iteration]] in [[Dynamic Programming in RL]]. Difference is that only use expected backups for sampled trajectories.
- Follow real or simulated trajectories
- At each visited state, do expected update
- Always act greedily wrt to current [[State Value]]

### Algorithm:
- Maintain 
	- V(s)
	- $P(S, A) \to R, S'$
- At each trial:
	- Start initial S
	- repeat till terminal:
		- Choose greedy action $$ a\gets\arg\max_a \sum_{s', r} \left(\hat p(s',r|s,a)\left[r+\gamma V(s') \right] \right)$$
		- update $$ V(s) \gets \max_a \sum_{s', r} \left(\hat p(s',r|s,a)\left[r+\gamma V(s') \right] \right)$$
		- move to next state