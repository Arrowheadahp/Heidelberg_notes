[[Temporal Difference Learning]] bootstraps after a single step. [[Monte-Carlo Methods]] waits till the end. N-Step [[Bootstrapping]] takes n real values and then bootstraps having a trade-off from the bias that comes from TD\[0\] and the variance that comes from MC methods. [[Bias Variance Tradeoff]].
This is still the same TD method but instead of changing an earlier estimate using the next step, it takes n steps later. 
The [[Universal Update Template]] becomes: $$ V(S_t) \to G_{t:t+n}= \sum_{i=1}^{n-1} \gamma^i R_{t+i} + \gamma^n V(S_{t+n}) $$
This allows the algorithm to look ahead n steps without the having to maximise rewards and create a 'strategy' to have rewards after n steps. It can still react fast but also wait long enough for the state to meaningfully change. 
- No updates for the n-1 steps of an episode
- After termination there are n-1 steps with 0 values are added.

### Why it works?
$$ \max_s | \mathbb E [G_{t:t+n} - v_\pi(s)|\le \gamma^n \max_s|V_{t+n-1}(s) - v_\pi(s)]
$$
Since $\gamma^n\le1$ repeated application shrinks the error and the worst error of the expected n-step return is at most $\gamma^n$ times the current error.

### Control
- [[On-Policy]]: [[N-Step SARSA]]
  A slight variation for reducing Variation is [[N-Step Expected SARSA]].
- [[Off-Policy]]: [[N-Step Off-Policy Learning]] 
  [[Q-Learning]] is a type of off-policy learning for TD and [[Off-Policy MC]] is for MC. To mitigate the issue that when $\rho=0$ the target collapses to 0 which causes variance. so the idea is to fold in a [[Control Variate]]. 