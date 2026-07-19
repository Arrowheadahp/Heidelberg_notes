The Environment is known: $$ p(s', r | s, a) = Pr(S_{t+1}=s', R_{t+1}=r| S_t = s, A_t=a) $$
> [!Question] If the model is known, how can we compute optimal behaviour without trial and error learning?
> Dynamic Programming solves the sequential decision problem, by repeatedly:
> 1. estimating how good the states are by [[policy evaluation]]
> 2. choosing better actions using those estimates by [[policy improvement]]
> 3. repeating the above 2 until nothing changes. This repetition is called [[Policy Iteration]] 


Dynamic Programming computes value functions and optimal policies by turning [[Bellman Equations]] into repeated update rules in [[Stationary Reinforcement Learning]]. 

### Cons:
- Dynamic Programming is often impractical since it requires a known model  which in turn many sweeps through the state space. Perfect model means that the [[State Value]] and the [[Action Value]] are known already. 
- Many RL algorithms can achieve the same effect without the perfect model and therefore less computation since there can be [[State]] that are very rare. 
### Pros:
-  It gives a conceptual template for prediction, Improvement and control.

### 2 ways to optimise:
1. [[Policy Iteration]]: Here, During each [[Policy Evaluation]], the [[Iterative Bellman Expectation Update]] happens until the $v_\pi$ stops changing. Then it goes to the [[Policy Improvement]]. Then it repeats until nothing changes.
2. [[Value Iteration]]: Here the [[Iterative Bellman Expectation Update]] is done only once before going to the [[Policy Improvement]]. This again repeats until nothing changes.


