2 Fundamental problems of RL:
1. [[Policy Evaluation]]: Given the [[Markov Decision Process]] and the [[Policy]] $\pi$, computing the expected [[Return]] at state s and for [[Action]] a. These expected values are written as [[State Value]] and [[Action Value]]. 
$$ v_\pi(s) = \mathbb{E}_\pi[G_t | S_t=s]
$$
2. [[Control Evaluation]]: Finding the best [[Policy]] $\pi$ that maximises the [[State Value]]. $$\pi^* \in arg\ max_\pi v_\pi(s) \ \forall s$$

To solve the problem of MDP, the [[Bellman Equations]] are used. 
