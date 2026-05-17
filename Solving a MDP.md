2 Fundamental problems of RL:
1. [[Policy Evaluation]]: Given the [[Finite Markov Decision Processes]] and the [[Policy]] $\pi$, computing the expected [[Return]] at state s and for [[Action]] a. These expected values are written as [[State Value Function]] and [[Action Value Function]]. 
$$ v_\pi(s) = \mathbb{E}_\pi[G_t | S_t=s]
$$
2. [[Control Evaluation]]: Finding the best [[Policy]] $\pi$ that maximises the [[State Value Function]]. $$\pi^* \in arg\ max_\pi v_\pi(s) \ \forall s$$

To solve the problem of MDP, the [[Bellman Equations]] are used. 
