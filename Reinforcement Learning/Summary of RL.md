#overview
### Value Function update Targets
[[State Value]]: Values must satisfy the [[Bellman Equations]] $$v_\pi(s)=\mathbb E_\pi(R_{t+1}+\gamma v_\pi(S_{t+1})|S_t=s) $$
Every learning algorithm enforces the same incremental rule as mentioned in [[Universal Update Template]] : $$V(S_t)\gets V(S_t) + \alpha(target-V(S_t))$$
We are going to the target in increments instead of going all at once because we can only sample the values, stepping $\alpha$ toward each noisy target averages the noise out and we get the [[Expected Values]] of the target. This is Stochastic approximation. Updates are O(1) and online and keeping the $\alpha$ constant keeps track of moving targets as well.

| Method                           | Target (V)                                   | Uses                            |
| -------------------------------- | -------------------------------------------- | ------------------------------- |
| [[Dynamic Programming in RL]]    | $\mathbb E[R_{t+1}+\gamma V(S_{t+1})]$       | Full model, no sampling         |
| [[Monte-Carlo Methods]]          | $G_t=\sum_{i=t}^T\gamma^{i-t}R_i$            | real returns only               |
| [[Temporal Difference Learning]] | $R_{t+1} + \gamma V(S_{t+1})$                | one real step + bootstrap       |
| [[N-Step Bootstrapping]]         | $\sum_{i=t}^{t+n}\gamma^{i-t}R_i+V(S_{t+n})$ | Between Monte Carlo and TD\[0\] |
| [[Function Approximation in RL]] | $R_{t+1}+\gamma \hat v(S_{t+1},w)$           | Bootstrap through $\hat v$      |
### Space of Updates:
Algorithms having high width are those that average over all next actions and states. Example: [[Dynamic Programming in RL]]. 
Algorithms that have high Depth are those that look the most deep. The depth depends on how many steps are taken before [[bootstrapping]]. High Depth: [[Monte-Carlo Methods]]. ![[Pasted image 20260716180024.png]]

### The Ultimate Goal
The real goal is to Maximise the Expected Return from [[Markov Decision Process]]. This Expected return when having a discount is called the [[State Value]].

What is being Learned?
1. Value based: learn $v$ or $q$ then act greedily
	1. [[Model]] known: $p(s',r|s,a)\forall s$
		1. [[Dynamic Programming in RL]]
		2. [[Policy Iteration]]
		3. [[Value Iteration]]
	2. Model Learned ([[Planning and Learning with Tabular Methods]])
		1. [[Background Planning]]
			1. [[Dyna-Q]]
			2. [[Dyna-Q+]]
			3. [[Prioritised Sweeping]]
		2. [[Decision Time Planning]]
			1. [[Heuristic Search RL]]
			2. [[Rollout Algorithm]]
			3. [[MCTS Monte Carlo Tree Search]]
		3. [[Trajectory Updates]]
			1. [[RTDP Real Time Dynamic Programming]]
	3. [[Model free RL]]: No model estimated. Here action value is estimated instead of state values.
		1. Maximum Depth: [[Monte-Carlo Methods]]
			1. [[On-Policy MC Control]]
			2. [[Off-Policy MC]]
		2. Minimum Depth [[Temporal Difference Learning]]
			1. [[On-Policy]]: 
				1. [[SARSA]]
			2. [[Off-Policy]]
				1. [[Q-Learning]]
				2. [[Double Q-Learning]]
		3. Depth controlled: [[N-Step Bootstrapping]]
			1. [[On-Policy]]
				1. [[N-Step SARSA]]
				2. [[N-Step Expected SARSA]]
			2. [[Off-Policy]]
				1. [[Control Variate]]
2. Policy Based: [[Policy Gradient Methods]]
	1. Without Baseline: [[REINFORCE]]
	2. With Learned Baseline: [[Actor-Critic Algorithm]]

### Generalized Policy Iteration
Every Value-based control algorithm is [[Generalized Policy Iteration (GPI)]] with different evaluation step.

| Algorithm                  | Evaluation           | Improvement      |     |
| -------------------------- | -------------------- | ---------------- | --- |
| [[Policy Iteration]]       | Repeated DP sweeps   | Greedy pure      |     |
| [[Value Iteration]]        | one DP backup        | greedy           |     |
| [[On-Policy MC Control]]]  | episode returns      | [[Epsilon-greedy]]   |     |
| [[SARSA]]                  | on policy TD[0]      | [[Epsilon-greedy]]   |     |
| [[Q-Learning]]             | [[Off-Policy]] TD[0] | greedy in target |     |
| [[Dyna-Q]], [[Dyna-Q+]]    | TD + simulated exp   | [[Epsilon-greedy]]   |     |
| [[Actor-Critic Algorithm]] | TD critic            | gradient ascent  |     |
- Evaluation makes values consistent with policy. $v_\pi \gets \pi$
- Improvement makes the policy greedy wrt value. $\pi\gets v\pi$
- Their only joint fixed point is optimality
- [[Policy Gradient Methods]] replace greedification by gradient ascent on $J(\theta)$ 
- [[Actor-Critic Algorithm]] keeps the [[Generalized Policy Iteration (GPI)]] in play
- [[REINFORCE]] has no Evaluation step at all.

Recurrent Trade-offs:
1. Bias vs Variance
2. samples vs compute (model-free vs planning)
3. exploration vs exploitation ([[Epsilon-greedy]], [[Upper Confidence Bounds Approach]])

Function Approximation + [[bootstrapping]]  + off policy can cause instability or divergence without additional safeguards.