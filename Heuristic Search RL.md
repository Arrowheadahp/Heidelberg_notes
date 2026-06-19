This is a [[Decision Time Planning]] algorithm.
- Spend Computation only on the current decision only
- Do not sweep the whole state space.

### Algorithm
- Build a look-ahead tree rooted at s
- Expand promising actions up to depth or budget limit
- Evaluate leaves with a heuristic or value estimate
- back up values from leaves to nodes
- Choose the root action with largest backed up value.