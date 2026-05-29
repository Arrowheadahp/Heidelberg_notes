Estimation of [[State Value Function]] is different between [[Monte-Carlo Methods]]  and [[Temporal Difference Learning]]. Where [[Monte-Carlo Methods]] goes over the whole episode and then updates all the states that it touched, [[Temporal Difference Learning]] initiates $v_\pi$ randomly and updates them continuously during an episode using the reward and the estimation of the next state.
$$ V(S_t) \gets V(S_t) + \alpha(R_{t+1} + \gamma V(S_{t+1}) - V(S_t))
$$
Here TD target is the value $V(S_t)$ is going towards.$$R_{t+1} + \gamma V(S_{t+1})$$The one step TD error is the difference between TD target and the current value.$$ \delta_t =  R_{t+1} + \gamma V(S_{t+1}) - V(S_t)$$
> [!NOTE] TD Error
> The Assignment is just finding the TD error and taking a gradient step on it.

### Algorithm:

- To calculate $v_\pi$ we need input $\pi$
- Initialize V(s) with V for terminal state =0
- For every episode
	- Initialize S
	- for every step of episode
		- $A\gets \pi(S)$
		- Take action A and get R and S'
		- $V(S) \gets V(S_t) + \alpha(R + \gamma V(S') - V(S))$
		- $S\gets S'$
		- Break when S is terminal

> [!Question] Why does the Bootstrapping work?
> For a fixed policy $\pi$, with a small constant, the mean of the V(S) converges to $v_\pi$ and for diminishing $\alpha$ satisfying the standard stochastic gradient descent conditions, V(S) converges to $v_\pi$ with probability 1.

The V(S) can be updated immediately like in the algorithm or it can be done by [[Batch Updating]]. 