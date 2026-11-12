This is a deeper greedy policy where instead of looking for the maximum of the next states, it looks at the maximum of the states n steps ahead. and takes that action.
This is a [[Decision Time Planning]] algorithm.
- Spend Computation only on the current decision only
- Do not sweep the whole state space.

### Algorithm
- Build a look-ahead tree rooted at s
- ==Expand promising actions up to depth== or budget limit. This is what makes it heuristic.
- Evaluate leaves with a heuristic or value estimate by averaging them.
- back up values from leaves to nodes
- Choose the root ==action with largest backed up value==.

![[Pasted image 20260721173516.png]]