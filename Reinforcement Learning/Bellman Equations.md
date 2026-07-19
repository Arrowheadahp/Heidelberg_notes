To calculate the [[State Value]], We need the [[Return]], which depends on the entire future trajectory. Bellman's Idea is to replace the huge path expectation by a recursive one-step decomposition. These are required for the [[Policy Evaluation]]. 

Bellman Expectation Equation for $v_\pi$
$$
v_\pi(s) = \sum_a \left(\pi(a|s) \sum_{s',r}p(s',r|s,a)\left[r+\gamma v_\pi(s')\right] \right)
$$
The expected [[Return]] for [[State]] s is the summation of choosing [[Action]] a given s multiplied with the summation of multiplication of probability of getting next state s' and reward r plus gamma \* expected return at state s'.

Bellman Expectation Equation for the [[Action Value]].  $q_\pi$
$$
q_\pi(s,a) = \sum_{s', r} \left(p(s',r|s,a)\left[r+\gamma \sum_{a'} \pi(a'|s')q_\pi(s',a')\right] \right)
$$
The expected [[Return]] for [[State]] s and action a is the summation of multiplication of probability of getting next state s' and reward r plus gamma \* expected return at state s'.

Relationship 
$$
v_\pi(s) = \sum_a \left(\pi(a|s) q_\pi(s,a) \right)
$$
$$
q_\pi(s,a) = \sum_{s', r} \left(p(s',r|s,a)\left[r+\gamma v_\pi (s')\right] \right)
$$
## Bellman's Optimality Equations

For the [[Control Evaluation]], we want to find the $\pi^*$. We say that $\pi$ is better than $\pi '$ if $v_\pi \geq v_{\pi '} \forall s$ 
$\pi^*$ is optimum when it is at least as good as every other policy at every state.

Optimal Value Function 
$$ v^*(s) = \max_{a \in A(s)} \left (\sum_{s',r}p(s',r|s,a)\left[r+\gamma v^*(s')\right] \right)
$$
Optimal Action Value Function
$$ q^*(s) = \max_{a \in A(s)} \left(\sum_{s',r}p(s',r|s,a)\left[r+\gamma \max_{a'}q^*(s',a')\right] \right)
$$
Relationship:
$$v^*(s) = \max_a q^*(s,a)
$$
## Greedy Policies
> [!NOTE] Greedy
> Any policy that is greedy with respect to v*(s) is optimal

We want the [[Policy]] that maximises the expected return at every state. 
$$
\pi_{greedy}(s) \in \arg \max_{a \in A(s)} \left(\sum_{s',r}p(s',r|s,a)\left[r+\gamma v^*(s')\right] \right)
$$
If the q* is known, then the equation becomes:
$$\pi_{greedy}(s) \in \arg max_a q^*(s,a)
$$
### Bellman optimality Operator T
Optimality operator T takes the [[State Value]] as input and returns a new value function TV. It is just a function that takes the whole list of state values and makes another list of state values by doing the following operation.
$$
(T v)(s) \gets \max_{a \in A(s)} \left (\sum_{s',r}p(s',r|s,a)\left[r+\gamma v(s')\right] \right)
$$
This assignment happens at every step
So at step k, 
$$ v_k \gets Tv_{k-1} $$
If repeated Bellman iterations stops changing the the value function, then we have found the fixed point $v^*$. The iteration is bound to reach the fixed point when $\gamma<1$ because the future contributions are shrunk.


