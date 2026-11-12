At Time t,
- [[Agent]] observes current situation (state $S_t$)
- It chooses [[Action]] $A_t$
- [[Environment]] responds with 
	- [[Reward]] $R_{t+1}$
	- [[State]] $S_{t+1}$
- This loops over time 
![[Pasted image 20260506233544.png]]

- It is a trial and error search
- The actions have delayed consequences

Definitions in Reinforcement Learning:
1. [[Agent]]: Learner and Decision maker
2. [[Action]] (A): Decision made by the agent at each step
3. [[Environment]]:This is the feedback $p(s', r | s, a) = Pr(S_{t+1}=s', R_{t+1}=r| S_t = s, A_t=a)$
4. [[State]] (S): The agent's situation and has all the info for decision making.
5. [[Reward]] (R): Scalar feedback for each action.
6. [[Policy]] ($\pi$): This is the probability of choosing action a at state s.
7. [[Return]] (G): Sum of rewards.
8. [[State Value]] $v_\pi(s) = \mathbb{E}_\pi[G_t | S_t=s]$: 
9. [[Action Value]] $q_\pi(s,a) = \mathbb E _\pi [G_t | S_t=s,A_t=a]$
10. [[Model]]: This is a model of the environment as learned by the agent.

Capital letters are [[Random Variables]]. Small letters are the specific values that the Random Variables can take.

### The goal is to get the optimal policy: $\pi^*=\arg\max_\pi \mathbb E_\pi[G_t]$ 