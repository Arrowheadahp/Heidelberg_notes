Main idea is Alternate between 
- [[Policy Evaluation]]
- [[Policy Improvement]]

### The [[Policy Iteration]] algorithm is:
1. Initialize a policy $\pi$
2. Loop forever: 
	1. Perform [[Iterative Bellman Expectation Update]] to compute $$v_{k+1}(s) \gets \sum_a \left(\pi(a|s) \sum_{s',r}p(s',r|s,a)\left[r+\gamma v_k(s')\right]\right)$$
	2. Perform [[Policy Improvement]] $$\pi(s) \gets \arg \max_{a \in A(s)} \left(\sum_{s',r}p(s',r|s,a)\left[r+\gamma v_\pi(s')\right] \right)$$
	3. If the [[Policy]] remains unchanged, then break. Otherwise repeat.
All of these are done using the [[Bellman Equations]].

> [!NOTE] Convergence
> For Finite [[Markov Decision Process]], the policy iteration eventually reaches an optimum policy $\pi^*$, which  is optimum when it is at least as good as every other policy at every state.

Since the number of deterministic policies are finite and after improvement step, the policy is at least as good as the previous one, therefore the policy can't improve forever. So it converges to the optimum policy $\pi ^*$.

