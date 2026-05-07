Bandits let us study learning from feedback without planning through time. Meaning: The [[State]] remains the same after every [[Action]]. But the [[Agent]] has to find the optimum [[Action]] because of chance. Example is 10 machines giving [[Gaussian Distribution]] [[Reward]]s but having different mean and standard deviations, so the [[Agent]] does not know which machine is optimum and it has to figure out the [[exploration]] vs [[exploitation]]. The means of the machines may also change over time. There is no future [[State]] or future [[Reward]].

The approaches to solve this problem differs by 
1. [[How the Q is calculated]]. 
2. How the actions are chosen to prioritise [[exploration]] vs [[exploitation]]. $\pi$
### Approaches:
1. [[Sample Averages and e-greedy]]: $\alpha=1/n$ , random action taken with probability e.
2. 

### Approach Testing
To test which approach is better, we create multiple k-armed bandits and run each approach (policies) and average them. 
- Here each arm has a random reward over a probability distribution with different expected values. 
- The arms differ across runs.
