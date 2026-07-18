Tabular means that all states and actions can be listed.
### Learning
The idea is to use the 'Learning' that we get from real experience (interacting with the environment) to create a memory (model)of the environment and do 'Planning' which is to optimise in that model.

This unifies the 
- [[Model based RL]]: The methods that has the model.
  Like [[Dynamic Programming in RL]]
- [[Model free RL]]: The methods that don't have the model.
  Ex: [[Temporal Difference Learning]], [[Monte-Carlo Methods]] etc.
The idea is that both type of methods rely on backups of the [[State Value]].

#### Model 
The [[Model]] is the knowledge of what reward and state will come when taking any action at any state. There are 2 types of model reconstruction:
- ==Distribution model==: All possible next states are rewards are present with their probabilities. The probabilities may come from prior knowledge:  $\hat p(s',r|s,a)\forall s$. 
  The update looks like [[Dynamic Programming in RL]]$$
Q_\pi(s, a) = \sum_{s', r} \left(\hat p(s',r|s,a)\left[r+\gamma \max_{a'} Q(s',a') \right] \right)
$$
- ==Sample Model==: Produces a single sampled next state and reward instead of the full probability distribution. This is much easier to obtain in practice. The update looks like $$Q(S, A) \gets Q(S, A) + \alpha(R + \gamma \max_a (Q(S', a)) - Q(S, A))$$

### Planning
Planning is any computational process that takes a model as input and produces or improves a policy. The model simulates the experience and the agent uses this experience to back up values and improve decisions.

### When a model is wrong:
Even when the model is getting filled with the correct transitions, 
- the [[Environment]] can be stochastic,
- not enough data is collected
- the environment can change like in [[Non-Stationary Reinforcement Learning]]
And a bad model can make the policy bad faster.
### Some Methods:
- [[Background Planning]]
	1. [[Dyna-Q]]
	2. [[Dyna-Q+]]: Variant of the [[Dyna-Q]] but has exploration bonus built in.
	3. [[Prioritised Sweeping]]: Prioritise the state actions where the Q value changes a lot.
-  [[Trajectory Updates]]: [[On-Policy]] Learning and planning
	1. [[RTDP Real Time Dynamic Programming]]: [[On-Policy]] trajectory-sampling version of value iteration
- [[Decision Time Planning]]
	1. [[Heuristic Search RL]]: Like Deeper Greedy Policy 
	2. [[Rollout Algorithm]]: This is a Decision time Monte Carlo Planning
	3. [[MCTS Monte Carlo Tree Search]]: Improving on [[Rollout Algorithm]] to get focus on promising branches