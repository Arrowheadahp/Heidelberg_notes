### Algorithm:
$$
v_{k+1}(s) \gets \max_a \left(\sum_{s', r} p(s', r|s, a) [r+\gamma v_k(s')]\right)
$$

Iterate until $$ \max_s (v_{k+1} - v_k) < \theta $$ Then we can take the $v^*=v_k$ and use [[Policy Improvement]].