This is the general [[Policy Iteration]] that is used to improve the policy $\pi$ in Reinforcement Learning. The pipeline is

1. Evaluate the current policy
2. Improve towards greediness
3. repeat
GPI is a class of algorithms that improves policies. 

[[Dynamic Programming in RL]] uses [[Policy Iteration]] for improving policies.


> [!Quote] GPI refers to the general idea of letting [[Policy Evaluation]] and [[Policy Improvement]] processes interact, independent of the granularity and other details of the 2 processes. Almost all reinforcement methods are well described as GPI.
