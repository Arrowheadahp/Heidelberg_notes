A variation of the [[N-Step SARSA]] where the bootstrap is done over all the actions available at $S_{t+n}$ multiplied by $\pi(a|S_{t+n})$. The [[Target Update]] is
$$ Q(S_t, A_t) \to G_{t:t+n} = \sum_{i=1}^{n-1} \gamma^i R_{t+i} + \gamma^n \left( \sum_a\pi(a|S_{t+n})Q(S_{t+n}, a) \right) $$
