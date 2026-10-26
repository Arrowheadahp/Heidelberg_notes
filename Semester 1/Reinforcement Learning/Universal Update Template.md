#todo 
The universal template for change when going from new to old is$$ new = old + \alpha(target-old) $$The alpha changes from approach to approach. 
- When $\alpha == 1/n$ then it is called the sample average.
- When $\alpha$ is constant, then the newer rewards are given more importance and the older rewards are $*\alpha^t$ so vanishes eventually.

Rephrased as $$ value \to target $$
$$S_t\to U_t$$
The target $U_t$ is (for prediction)
- [[Dynamic Programming in RL]]: $$U_t = \sum_a\left( \pi(s, a)\sum_{s', r} p(s', r|s,a)\left(r+ \gamma v_\pi(s')\right) \right) $$
- [[Monte-Carlo Methods]]: $$U_t = G_t = \sum_{k=t}^{T-1} \gamma^{k-t}\cdot  r_{k+1}$$
- [[Temporal Difference Learning]]: $$U_t = R_{t+1} + \gamma v_{t+1} $$
- [[N-Step Bootstrapping]]: $$U_t = G_{t:t+n} = \left( \sum_{k=t}^{\min(T-1, n+t)}\gamma^{k-t}\cdot r_{k+1}\right) +\gamma^n v_{t+n}$$
