We need a $\varepsilon$-soft policy for [[exploration]]. Meaning $$ \pi(a|s) \geq \frac{\varepsilon}{|A(s)|} \forall s, \forall a \in A(s), \varepsilon > 0
$$
[[Why eta-Soft used for Improvement]]
The simplest one is [[Eta-greedy]] method, 

$$ Pr(A_t = a_g) = 1- \varepsilon +\frac{\varepsilon}{|A(s)|} $$$$ Pr(A_t = a) = \frac{\varepsilon}{|A(s)|} $$
But any methods in [[exploration]] should work here.

### Calculating the $q_\pi(s,a)$

$$q_\pi(s,\pi'(s)) = (1-\varepsilon)\max_a q_\pi(s,a) + \frac{\varepsilon}{|A(s)|}\sum_a q_\pi(s,a)
$$
### Algorithm:

- Initialize Q(s,a) with arbitrary values.
- For each episode:
	- generate episode with policy $\pi$.
	- Evaluate policy using [[MC Prediction]].
	- Improve policy $$ \pi(a|s) \gets \pi_{greedy}'(s) \in \arg \max_a q(s,a) $$