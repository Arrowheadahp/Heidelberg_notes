[[Q-Learning]] target is $$ R_{t+1} + \gamma \max_a Q(S_{t+1}, a)$$ 
And therefore the update equation becomes
$$Q(S_t, A_t) \gets Q(S_t, A_t)+\alpha( R_{t+1}+\gamma \max_a Q (S_{t+1}, a) - Q(S_t, A_t))$$

This means that that [[Q-Learning]] always learns the value of the greedy policy regardless of the action it takes. 

Exploration Policy can be any [[Eta-greedy]] so that every (s,a) pair is visited infinitely often
Target Policy is pure greedy wrt to current estimation of Q
The 2 may be different.

### Algorithm

- Get Step Size $\alpha,\varepsilon \in (0, 1]$
- Initialize Q(s, a) with Q(terminal state, .) = 0
- For every episode
	- Initialize S
	- for every step of episode
		- $A\gets \pi(S)$
		- Take action A and get R and S'
		- $Q(S,A) \gets Q(S,A) + \alpha(R + \gamma \max_a Q(S_{t+1}, a) -Q(S,A))$
		- $S\gets S'$
		- break when S is terminal

This is the heart of the model-free greedy control: sample successor, max over actions.

> [!Note] Since [[Q-Learning]] keeps on exploring, it has a higher chance of going over a cliff. Meaning it will keep exploring bad states actions with very negative rewards.

