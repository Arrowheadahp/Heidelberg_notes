
What function approximation does is 
- a compact representation of the state
- knowledge of which states are similar

Replacing the table V(s) by parameterized approximations. Meaning instead of a table `V`for storing the [[State Value Function]], we can use a [[Machine Learning]] algorithm to approximate the value using parameters (weights). This gives in built generalization.

$$ \hat v(s, w) \approx v_\pi(s) $$
Where w is the parameters (weight vector) that has much less number of values than number of states. We update the w incrementally.

- Linear: $\hat v(s,w)=w^Tx(s)$
- [[Neural Network]] where $\hat v$ is a MLP
- [[Decision Trees]]
- Memory based/ Kernel Methods

RL produces a stream of [[Target Update]] or training examples for the function approximator to fit. 

### Problems with Function Approximation

- Learning is online
- For a policy, we only get info for the visited states
- Bootstrapping has bias and target depends on current weights.
- Non-stationary: Changing the value function changes the policy  which changes the future data distribution.

