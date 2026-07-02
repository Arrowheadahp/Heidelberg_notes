
> [!Question] How do we evaluate a policy when we cannot store one number per state, and almost every state we encounter is effectively new?

### The problem
[[Planning and Learning with Tabular Methods]] break when the number of states are so high that most states encountered during learning is effectively new. With a state space so large, storing even a single value for each state gets expensive. 
Some examples:
- continuous state spaces (sensors, joint angles)
- Very high dimensional data (images, structured descriptions)
- Combinatorial (positions of many objects: chess)

> [!Idea] The idea is therefore to GENERALIZE the values of the states the agent has seen to the states it hasn't by exploiting regularities. 

### [[Function Approximation in RL]]
The Idea is to use [[Function Approximation in RL]]. Replacing the table V(s) by parameterized approximations. Meaning instead of a table `V`for storing the [[State Value Function]], we can use a [[Machine Learning]] algorithm to approximate the value using parameters (weights). This gives in built generalization.

$$ \hat v(s, w) \approx v_\pi(s) $$
Where w is the parameters (weight vector) that has much less number of values than number of states. We update the w incrementally.
