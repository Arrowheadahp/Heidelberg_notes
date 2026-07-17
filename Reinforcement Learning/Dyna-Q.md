The main idea is to 
1. Acting: Interact with the environment
2. Direct RL: learn from the real experience
3. Model Learning: Learn and improve the model `M` from that experience
4. Planning: Learn from simulated experience.

The model would be a memory of all the states and rewards that the agent got in the real environment at a state doing action. `M[S, A] = (R, S')`

### Algorithm

- Maintain
	- [[State Value Function]] `Q(S, A)`
	- Model `M[S, A] = (R, S')`
	- Set of previously seen state action pairs
- Per real state:
	- Choose a from s by $\varepsilon$-greedy on `Q`
	- execute a, observe r, s'
	- Direct RL update [[Q-Learning]]: $$Q(S_t, A_t) \gets Q(S_t, A_t)+\alpha( R_{t+1}+\gamma \max_a Q (S_{t+1}, a) - Q(S_t, A_t))$$
	- Store model entry $M[s,a] \gets (r, s')$
	- Repeat n times:
		- sample old `sp, ap` randomly
		- get $rp, s'p \gets M[sp, ap]$
		- update `Q(S,A)` using [[Q-Learning]]
	- $s\gets s'$

### Why it works
Without planning, only a tiny region gets backed up. But with planning, the information gets propagated much further. It simulates already what will happen before it happens in the environment.