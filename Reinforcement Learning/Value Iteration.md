### Algorithm:
$$
V_{k+1}(s) \gets \max_a \left(\sum_{s', r} p(s', r|s, a) [r+\gamma V_k(s')]\right)
$$
This is the Bellman Optimality operator in [[Bellman Equations]].
Iterate until $$ \max_s (V_{k+1} - V_k) < \theta $$ Then we can take the $v^*=v_k$ and use [[Policy Improvement]]. 