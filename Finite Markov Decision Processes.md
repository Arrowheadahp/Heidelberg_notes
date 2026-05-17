> [!question] Guiding Question
> How do we evaluate actions when it affects not just the immediate reward but also the future states they lead to?

Core properties of MDP:
- Evaluative Feedback: we observe a scalar [[Reward]] signal.
- Associative Setting: Best [[action]] depends **only** on the the current [[State]].
- Delayed consequences: effect of an [[Action]] may show up much later.
- Credit assignment: Which earlier decision caused later [[reward]].

MDPs are the standard mathematical model for sequential decision making under uncertainty.
![[Pasted image 20260508205403.png|400]]
[[Multi-Armed Bandits]] only simulated the one-step decision problem where there was immediate [[Reward]] and no future [[State]]. 
- In MDP, the [[action]] not only decides the reward but also the next state that it leads to according to $p(s', r|s,a)$. This is called the [[Environment]]. 
- Every [[State]] has their own options of actions that can be taken from their state which can be taken according to policy $\pi(a|s)$. 
- Every state has it's own expected rewards $v_\pi(s)$.
- Every state action pair also has it's own expected reward $q_\pi(s, a)$.

Tabular setting is when the number of states is finite so v(s) and q(s,a) can be stored in tables in [[Dynamic Programming in RL]]. Otherwise when the $S$ is huge, or continuous, then these calculations need to be done by function approximations.