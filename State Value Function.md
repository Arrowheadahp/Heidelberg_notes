The state value function is defined as the expected [[Return]] from state s. It averages over all future random draws from both the [[Policy]] and the [[Environment]].
$$ v_\pi(s) = \mathbb{E}_\pi[G_t | S_t=s]
$$Relationship with [[Action Value Function]]
$$
v_\pi(s) = \sum_a \left(\pi(a|s) q_\pi(s,a) \right)
$$

| Method                           | Target (V)                                   | Uses                            |
| -------------------------------- | -------------------------------------------- | ------------------------------- |
| [[Monte-Carlo Methods]]          | $G_t=\sum_{i=t}^T\gamma^{i-t}R_i$            | real returns only               |
| [[Temporal Difference Learning]] | $R_{t+1} + \gamma V(S_{t+1})$                | one real step + bootstrap       |
| [[N-Step Bootstrapping]]         | $\sum_{i=t}^{t+n}\gamma^{i-t}R_i+V(S_{t+n})$ | Between Monte Carlo and TD\[0\] |
| [[Dynamic Programming in RL]]    | $\mathbb E[R_{t+1}+\gamma V(S_{t+1})]$       | Full model, no sampling         |
| [[Function Approximation in RL]] | $R_{t+1}+\gamma \hat v(S_{t+1},w)$           | Bootstrap through $\hat v$      |
