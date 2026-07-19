Let ==Transition Matrix== P be the probability of transitioning from $s_i \to s_j$.  $$(P_\pi)_{ij} \gets \sum_a \pi(a|s_i)P(s_j|s_i, a)$$
 So $$ v_{k+1} \gets r_\pi + \gamma P_\pi v_k
 $$
 The above operation is called the Bellman Expectation Operation. So the Bellman Expectation Operator $T_\pi v=r_\pi + \gamma P_\pi v_k$

 After enough iterations such that the v does not change enough, the final equation comes to be: 
 $$ v^*_\pi = r_\pi + \gamma P_\pi v_\pi^* $$
 $$ v^*_\pi = (\mathbb{I}-\gamma P_\pi)^{-1} r_\pi $$
 This is a way to solve the [[Bellman Equations]] but the [[Iterative Bellman Expectation Update]] is preferred since the calculations are $O(s^3)$ and the transition matrix P gets typically very large and sparse. 