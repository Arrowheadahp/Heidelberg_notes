> [!Question] Can we take better actions at a given state?
> 

Instead of Following [[Policy]] $\pi$ from the beginning, we do [[action]] a first and then follow policy $\pi$ afterwards.

The measurement of how good it is to take action a now and then following policy $\pi$ afterwards is given as [[Action Value Function]]. $$
q_\pi(s, a) = \sum_{s', r} \left(p(s',r|s,a)\left[r+\gamma v_\pi(s')\right] \right)
$$
If $q_\pi(s) > v_\pi(s)$, then taking a once and then following the policy is better than following policy $\pi$ immediately.

> If one deviation improves the expected [[Return]], then permanently switching towards that action should improve the [[Policy]].


### Generalizing:

Similarly taking action using policy $\pi'$ first then policy $\pi$ afterward improves the expected return, then new policy is better.
If $$ q_\pi(s,\pi'/(s)) \geq v_\pi(s) $$
then $$ v_{\pi '}(s) \geq v_\pi(s) $$
### Greedy Policy improvement

Given a policy $\pi$, We define a new policy $\pi '$ choosing the action with the highest [[Action Value Function]]:
$$\pi_{greedy}'(s) \in \arg max_a q^*(s,a)
$$
We want the [[Policy]] that maximises the expected return at every state. 
$$
\pi_{greedy}'(s) \in \arg \max_{a \in A(s)} \left(\sum_{s',r}p(s',r|s,a)\left[r+\gamma v_\pi(s')\right] \right)
$$

> [!NOTE] Garuntee
> A greedy policy wrt $v_\pi$ is garunteed to be at least as good as the original policy.


