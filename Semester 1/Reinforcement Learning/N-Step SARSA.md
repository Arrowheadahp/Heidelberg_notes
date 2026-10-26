This is just like [[SARSA]] but instead of looking only 1 step ahead,  it looks n steps ahead. The [[Universal Update Template]] is
$$ Q(S_t, A_t) \to G_{t:t+n} = \sum_{i=1}^{n-1} \gamma^i R_{t+i} + \gamma^n Q(S_{t+n}, A_{t+n}) $$
### Algorithm
Just like [[SARSA]], this also needs a policy that is [[GLIE (Greedy in the Limit with Infinite Exploration)]].

![[Pasted image 20260612005643.png]]

### N-Step Expected SARSA
A variation is the N-Step Expected SARSA where the bootstrap is done over all the actions available at $S_{t+n}$ multiplied by $\pi(a|S_{t+n})$ is the [[N-Step Expected SARSA]].
$$ Q(S_t, A_t) \to G_{t:t+n} = \sum_{i=1}^{n-1} \gamma^i R_{t+i} + \gamma^n \left( \sum_a\pi(a|S_{t+n})Q(S_{t+n}, a) \right) $$