
> [!Question] Guiding Question
> Can we update our value estimates using current estimates as targets? Why Does it work and when is it beneficial over waiting for actual returns?

Temporal Difference Learning is a [[Model]] free RL method that limits the number of steps ahead the return will take the real rewards and then bootstraps the rest. 
### Advantages of TD:
1. TD requires only sampled transitions and can update after one single transition using $S_t, R_{t+1}, S_{t+1}$
2. [[Online Learning]] where data is streamed, TD is a natural fit.
3. Empirically TD reduces error rate faster than MC.
4. TD(0) converges to Certainty equivalence principal which DP gets using the environment. 
5. TD does it with $O(N)$ memory and $O(N)$ time.
6. For large state spaces, therefore TD is the only feasible way to approximate the Certainty equivalence principal.

[[Comparison between DP, MC, TD]]
### Prediction
[[Temporal Difference Learning]] initiates $v_\pi$ randomly and updates them continuously using [[TD Prediction]]. $$ V(S_t) \gets V(S_t) + \alpha(R_{t+1} + \gamma V(S_{t+1}) - V(S_t))
$$
### Control
Control follows the [[Generalized Policy Iteration (GPI)]]. With TD, Evaluation and Iteration is interleaved
- Updates happen step-by-step within each episode
- The policy changes as soon as $Q$ changes.
For model-free control, we learn the [[Action Value Function]] $Q(s, a)$ just like in MC.

There are 2 types of Control
1. [[On-Policy]] where the both exploration and exploitation is using the same policy. In TD [[SARSA]] is the method used for this.
2. [[Off-Policy]] where the exploration and exploitation is done by different policies. [[Q-Learning]] is the method. To mitigate the issues like Bias, [[Double Q-Learning]] is used.


> [!NOTE] TD and MC does not give the same fixed point ($v^*$) even for the same data
> This is because [[Monte-Carlo Methods]] gives the mean (reduces the mean square error) of the observed data
> [[Temporal Difference Learning]] gives the maximum likelihood of the state values. It is the exact solution on the inferred Markov model would give

