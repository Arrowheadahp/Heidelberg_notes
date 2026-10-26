If the any policy follows the [GLIE (Greedy in the Limit with Infinite Exploration)](app://obsidian.md/GLIE%20\(Greedy%20in%20the%20Limit%20with%20Infinite%20Exploration\)), then it will converge.
- Exploration: All (s,a) visited infinitely often. ([[Epsilon-soft]])$$ \pi(a|s) \geq \frac{\varepsilon}{|A(s)|} \forall s, \forall a \in A(s), \varepsilon > 0
$$
- Greediness in the limit: Policy becomes greedy wrt Q when $t \to \infty$

[[Epsilon-greedy]] is [[GLIE (Greedy in the Limit with Infinite Exploration)]] when $\varepsilon$ decreases with time.