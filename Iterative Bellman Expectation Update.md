A Bellman backup updates one state by looking one step ahead and using current value estimates for successor states.

- We start with a random values for $v_0(s)$ and then ==repeatedly== apply the Bellman expectation update. This is called [[Bootstrapping]]. 
	- Provided the $v_k$, we get the [[State Value]] for the next step using $$v_{k+1}(s) \gets \sum_a \left(\pi(a|s) \sum_{s',r}p(s',r|s,a)\left[r+\gamma v_k(s')\right]\right)$$
- For discounted values, $\gamma<1$ these updates converges to $v_\pi$.
- We can overwrite the old values immediately or we can store the old values in a new array V' and then point the old array V to the new one at the end of an iteration.
- We continue doing the updates until the max change in the update is < threshold.


> [!NOTE] Intuition
> Each update moves the value vector closer to the unique fixed point $v_\pi$.
