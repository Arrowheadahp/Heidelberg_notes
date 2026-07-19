We need a $\varepsilon$-soft policy for [[Exploration]]. Meaning $$ \pi(a|s) \geq \frac{\varepsilon}{|A(s)|} \forall s, \forall a \in A(s), \varepsilon > 0
$$But any policy where the above criteria is satisfied can be used for the exploration. Here we take the [[Epsilon-greedy]].
### Why even with forced exploration, [[Epsilon-greedy]] policy improves the old soft policy.
#todo 
### Calculating the $q_\pi(s,a)$

$$q_\pi(s,\pi'(s)) = (1-\varepsilon)\max_a q_\pi(s,a) + \frac{\varepsilon}{|A(s)|}\sum_a q_\pi(s,a)
$$
### Algorithm:

- Initialize Q(s,a) with arbitrary values. 
- Choose a policy $\pi$ which is $\varepsilon$ soft.
- For each episode:
	- generate episode with policy $\pi$.
	- Evaluate policy using [[MC Prediction]]. 
	- Improve policy $$ \pi(a|s) \gets \pi_{greedy}'(s) \in \arg \max_a q(s,a) $$

