> [!question] Guiding Question
> How do we evaluate actions when it affects not just the immediate reward but also the future states they lead to?

[[What is a Finite Markov Decision Process]]
[[Multi-Armed Bandits]] only simulated the one-step decision problem where there was immediate [[Reward]] and no future [[State]]. In MDP, the [[action]] not only decides the reward but also the next state that it leads to according to $p(s', r|s,a)$. This is called the [[Environment]] that gives a scalar [[reward]] $R_{t+1}$ as well as a [[state]] $S_{t+1}$ when taking [[action]] a at the [[state]] s.
$$ p(s', r | s, a) = Pr(S_{t+1}=s', R_{t+1}=r| S_t = s, A_t=a) $$MDPs are the standard mathematical model for sequential decision making under uncertainty.

Properties of MDP:
1. The probability of going to a state s' while doing an action at state s only depends on the state s.

Solving every MDP requires 2 fundamental parts:
1. Prediction ([[Policy Evaluation]]): To get the [[State Value]] and [[Action Value]] for a specific [[Policy]]
2. Control: ([[Policy Improvement]]): To use the Values to improve the [[Policy]].

To solve the above 2 problems, [[Bellman Equations]] are used

