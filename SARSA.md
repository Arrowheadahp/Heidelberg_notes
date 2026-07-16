SARSA means $S_t, A_t, R_{t+1}, S_{t+1}, A_{t+1}$

This is the [[On-Policy]] Control Method for [[Temporal Difference Learning]] and calculates the [[Action Value Function]] using the bootstrapped estimate of the [[Action Value Function]] of the next state action pair.

$$Q(S_t, A_t) \gets Q(S_t, A_t)+\alpha( R_{t+1}+\gamma Q (S_{t+1}, A_{t+1}) - Q(S_t, A_t))$$
$A_t, A_{t+1}$ are actions taken under the current policy $\pi$. If $S_{t+1}$ is terminal, then TD target is $R_{t+1}$. 
The [[SARSA]] target is $$ R_{t+1} + \gamma Q(S_{t+1}, A_{t+1})$$
> [!Remark] Calculating Q instead of V
> I am thinking of each (s, a) as a state instead of s and navigating the decision tree from there.
### Algorithm

- Get Step Size $\alpha,\varepsilon \in (0, 1]$
- Initialize Q(s, a) with Q(terminal state, .) = 0
- For every episode
	- Initialize S
	- for every step of episode
		- $A\gets \pi(S)$
		- Take action A and get R and S'
		- if S' is terminal
			- $Q(S,A) \gets Q(S,A) + \alpha(R-Q(S,A))$
			- break
		- $A'\gets \pi(S')$
		- $Q(S,A) \gets Q(S,A) + \alpha(R + \gamma Q(S', A') -Q(S,A))$
		- $S\gets S'$
		- $A\gets A'$


> [!NOTE] SARSA interleaves evaluation and improvement
> Each TD update evaluates the current policy a little, and each $\varepsilon$-greedy action choice improves behaviour a little


> [!Question] Will SARSA Converge?
> If the any policy follows the [[GLIE (Greedy in the Limit with Infinite Exploration)]], then it will converge.

