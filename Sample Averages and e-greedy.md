## Sample Averages

- Let $N_t(a)$ = number of times action a has been selected before time t
- A natural estimate of potential rewards is the empirical mean of the rewards from the action $$Q_t(a) = \frac{\sum_{i=1}^{t-1}R_i*1}{\sum_{i=1}^{t-1}1} = \frac{1}{N_t(a) }\sum_{A_i=a}R_i $$
- The update function would look like $$ Q_{n+1} = Q_n + \frac{1}{n}(R_n - Q_n) $$ Which means that the Q of the next step is getting updated from the previous estmation by the value that is going towards the [[Reward]] got. new = old + $\alpha$(target-old) 
- 
- This Q will always converge to the real value $Q^*$ when we are going for [[Stationary Reinforcement Learning]] problem.
- The action $A_t$ chosen acording to $Q_t$. 
## $\varepsilon$ greedy method
We can always choose the action that has the maximum $Q_t$ which will improve the reward now. But it won't find the correct Qs until it explores the whole space. But the that [[exploration]] will improve future decisions but the current rewards will be low. So we choose a random action with probability $\epsilon$ and otherwise choose the action with maximum $Q_t$. 

Therefore, $$ Pr*A_t = a_g) = 1- \epsilon (1-1/k) $$ where $a_g$ is the greedy choice.

> $\epsilon$- greedy algorithm garuntees that even bad actions keep getting sampled to check if it gives better results later.

### Cons
1. Sample averages weigh old and new rewards equally. which is good when the reward probability distribution does not change. But it is bad when true value drifts over time. For that the $\alpha$ can be kept constant.