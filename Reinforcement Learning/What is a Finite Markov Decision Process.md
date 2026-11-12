
[[Multi-Armed Bandits]] only simulated the one-step decision problem where there was immediate [[Reward]] and no future [[State]]. 
- In MDP, the [[action]] not only decides the reward but also the next state that it leads to according to $p(s', r|s,a)$. This is called the [[Environment]] that gives a scalar [[reward]] $R_{t+1}$ as well as a [[state]] $S_{t+1}$ when taking [[action]] a at the [[state]] s.
$$ p(s', r | s, a) = Pr(S_{t+1}=s', R_{t+1}=r| S_t = s, A_t=a) $$
- Every [[State]] has their own options of actions that can be taken from their state which can be taken according to policy $\pi(a|s)$. 
![[Pasted image 20260508205403.png|400]]
Core [[Properties of Decision Processes]]:
- Evaluative Feedback: we observe a scalar [[Reward]] signal.
- Associative Setting: [[action]] depends ==only== on the the current [[State]]. This is the Markov property.
- Delayed consequences: effect of an [[Action]] may show up much later.
- Credit assignment: Which earlier decision caused later [[reward]].

MDPs are the standard mathematical model for sequential decision making under uncertainty.

> [!NOTE] Finite / Tabular
> Tabular setting is when the number of states is finite so v(s) and q(s,a) can be stored in tables in [[Dynamic Programming in RL]]. Otherwise when the $S$ is huge, or continuous, then these calculations need to be done by function approximations.

> [!NOTE] Markov Property
> The future actions and rewards and states only depends on the current state and action but not the past. The state contains all the information needed to predict the the future.
