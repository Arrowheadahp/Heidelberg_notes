Alternate between 
- [[Policy Evaluation]]
- [[Policy Improvement]]

The [[Policy Iteration]] algorithm is:
1. Initialize a policy $\pi$
2. Perform [[Policy Evaluation]] to compute $v_\pi$
3. Perform [[Policy Improvement]] $$\pi(s) \gets \arg \max_{a \in A(s)} \left(\sum_{s',r}p(s',r|s,a)\left[r+\gamma v_\pi(s')\right] \right)$$
4. If the [[Policy]] remains unchanged, then stop. Otherwise repeat.
All of these are done using the [[Bellman Equations]].

> [!NOTE] Convergence
> For Finite [[Markov Decision Processes]], the policy iteration eventually reaches an optimum policy $\pi^*$, which  is optimum when it is at least as good as every other policy at every state.

Since the number of deterministic policies are finite and after improvement step, the policy is at least as good as the previous one, therefore the policy can't improve forever. So it converges to the optimum policy $\pi ^*$.

