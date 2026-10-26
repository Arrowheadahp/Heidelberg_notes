## $\varepsilon$ greedy method
We can always choose the action that has the maximum $Q_t$ which will improve the reward now. But it won't find the correct Qs until it explores the whole space. But the that [[Exploration]] will improve future decisions but the current rewards will be low. So we choose a random action with probability $\epsilon$ and otherwise choose the action with maximum $Q_t$. 

Therefore, $$ Pr(A_t = a_g) = 1- \varepsilon +\frac{\varepsilon}{k} $$ where $a_g$ is the greedy choice.
Otherwise, $$ Pr(A_t = a) = \frac{\varepsilon}{k} $$

> $\epsilon$- greedy algorithm guarantees that even bad actions keep getting sampled to check if it gives better results later.

### Cons
1. Sample averages weigh old and new rewards equally. which is good when the reward probability distribution does not change. But it is bad when true value drifts over time. For that the $\alpha$ can be kept constant.