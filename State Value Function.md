The state value function is defined as the expected [[Return]] from state s. It averages over all future random draws from both the [[Policy]] and the [[Environment]].
$$ v_\pi(s) = \mathbb{E}_\pi[G_t | S_t=s]
$$Bellman Expectation Equation for $v_\pi$
$$
v_\pi(s) = \sum_a \left(\pi(a|s) \sum_{s',r}p(s',r|s,a)\left[r+\gamma v_\pi(s')\right] \right)
$$Relationship with [[Action Value Function]]
$$
v_\pi(s) = \sum_a \left(\pi(a|s) q_\pi(s,a) \right)
$$