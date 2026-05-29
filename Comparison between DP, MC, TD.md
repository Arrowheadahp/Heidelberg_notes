| [[Dynamic Programming in RL]] | [[Monte-Carlo Methods]] | [[Temporal Difference Learning]] |
| ----------------------------- | ----------------------- | -------------------------------- |
| model + [[Bootstrapping]]     | samples, no bootstrap   | samples + bootstrap              |
| Full expectation backup       | complete return         | one step sample return           |
Here Sampling means interacting with the [[Environment]] and getting the $R_{t+1}$ and $S_{t+1}$.
[[Dynamic Programming in RL]] already knows the environment and simulates it to get the [[State Value Function]].


### Advantages of using TD over MC:
1. MC must wait for the whole episode to end to get the value $G_t$. but TD requires only sampled transitions and can update after one single transition using $S_t, R_{t+1}, S_{t+1}$
	1. Some applications having very long episodes or are [[Continuing Tasks]] are too slow or cannot be completed by MC.
	2. [[Online Learning]] where data is streamed, TD is a natural fit.
2. Empirically TD reduces error rate faster than MC.

### Advantages of TD over DP:
1. TD(0) converges to Certainty equivalence principal which DP gets using the environment. 
   TD estimates the $p(s\to s')$ and the reward $r(s\to s')$. Treating these estimates as true model, Solving the Bellman Equations gives the certainty Equivalence Principal.
   TD is doing model estimation and planning without ever building the model explicitly.
2. For $N=|S|$, 
	1. DP requires $O(N^2)$ memory and solving the [[Bellman Equations]] requires $O(N^3)$
	2. TD does it with $O(N)$ memory and $O(N)$ time.
3. For large state spaces, therefore TD is the only feasible way to approximate the Certainty equivalence principal.