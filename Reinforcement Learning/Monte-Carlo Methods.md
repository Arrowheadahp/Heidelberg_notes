 > [!question] Guiding Question
> How do we evaluate and improve a policy when there is no model of the environment, only sampled trajectories?

Where [[Dynamic Programming in RL]] requires a complete model $p(s',r|s,a)\forall s$. [[Monte-Carlo Methods]] is a [[Model free RL]] that computes [[State Value]] using [[Expectation Backups]] which is more relevant to real life scenarios where the model is unknown or intractable.

Input: Sampled experience formulated for [[Episodic Tasks]]. Like: $$ S_0, A_0, R_1, S_1, A_1, R_2, S_2, A_2, ... S_T$$
[[Return]] from time t: $$G_{t_i}:=\sum_{k=0}^{T-t_i-1} \gamma^k R_{t_i+k+1}$$
 >[[Monte-Carlo Methods]] do not use [[Bootstrapping]]. It estimates values directly from complete returns using [[MC Prediction]] and do not use value estimates in their updates.$$ V(s) \gets V(s) + \frac{1}{N(s)} \left(G - V(s) \right)$$
## Types of MC
If policy $\pi$ is deterministic, then there will not be any [[Exploration]] and reliable improvement is impossible. We need to enforce exploration while still improving. For this there are 2 ways to enforce exploration:
1. [[On-Policy]] Monte Carlo:
	1. Evaluation of state value: [[MC Prediction]]
	2. Improvement of policy: [[On-Policy MC Control]]
2. [[Off-Policy MC]]
	1. [[Off-Policy MC Prediction]]
	2. [[Off-Policy MC Control]]
	
Both uses [[MC Improvement]] to improve the target policy.
### Pros:
1. Unbiased: targets are actual outcomes
2. No model needed
3. Simple
### Cons:
1. Updates delayed till episode end
2. Higher Variance than [[Bootstrapping]] methods