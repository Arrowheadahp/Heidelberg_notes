Action Value Function is defined as the expected [[Return]] when choosing [[Action]] a at [[State]] s. 
$$
q_\pi(s,a) = \mathbb E _\pi [G_t | S_t=s,A_t=a] 
$$
The measurement of how good it is to take action a now and then following policy $\pi$ afterwards.
$$
q_\pi(s, a) = \sum_{s', r} \left(p(s',r|s,a)\left[r+\gamma v_\pi(s')\right] \right)
$$
Relationship with [[State Value]]
$$
q_\pi(s,a) = \sum_{s', r} \left(p(s',r|s,a)\left[r+\gamma \sum_{a'} \pi(a'|s')q_\pi(s',a')\right] \right)
$$
