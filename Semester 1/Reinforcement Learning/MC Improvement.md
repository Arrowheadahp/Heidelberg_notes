When Model is available, we do [[Policy Improvement]] by $$
\pi_{greedy}'(s) \in \arg \max_{a \in A(s)} \left(\sum_{s',r}p(s',r|s,a)\left[r+\gamma v_\pi(s')\right] \right)
$$
But in [[Monte-Carlo Methods]], we don't have the a complete model $p(s',r|s,a)\forall s$.

The solution is to compute the [[Action Value Function]] directly:
$$ q_\pi(s,a) = \mathbb E _\pi [G_t | S_t=s,A_t=a] \approx \frac{1}{n}\sum_{i=1}^n G_i(s,a)
$$
Once $q_\pi$ is known, improvement is trivial. $$\pi_{greedy}'(s) \in \arg \max_a q^*(s,a)
$$