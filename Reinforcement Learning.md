Reinforcement Learning is learning what to do, mapping situations to actions, in order to maximise cumulative reward.
The agent is not told the correct [[action]], but it has to learn from the consequences of its own actions which affect both the immediate reward and the future situations and future rewards.

1. [[Definitions in Reinforcement Learning|Introduction to RL]] 
2. [[Multi-Armed Bandits]]:
    [[exploration]] vs [[exploitation]] dilemma
3. [[Finite Markov Decision Processes]]: 
    Sequential Decision Making
4. [[Dynamic Programming in RL]] 

Fundamental problems of RL:
1. [[Policy Evaluation]]: Given the [[Finite Markov Decision Processes]] and the [[Policy]] $\pi$, computing the expected [[Return]] at state s and for [[Action]] a. These expected values are written as [[State Value Function]] and [[Action Value Function]]. 
$$ v_\pi(s) = \mathbb{E}_\pi[G_t | S_t=s]
$$
2. [[Control Evaluation]]: Finding the best [[Policy]] $\pi$ that maximises the [[State Value Function]]. $$\pi^* \in arg\ max_\pi v_\pi(s) \ \forall s$$