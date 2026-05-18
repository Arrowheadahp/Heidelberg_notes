> [!question] Guiding Question
> How do we evaluate actions when it affects not just the immediate reward but also the future states they lead to?

1. [[What is a Finite Markov Decision Process]]
   [[Multi-Armed Bandits]] only simulated the one-step decision problem where there was immediate [[Reward]] and no future [[State]]. In MDP, the [[action]] not only decides the reward but also the next state that it leads to according to $p(s', r|s,a)$. This is called the [[Environment]] that gives a scalar [[reward]] $R_{t+1}$ as well as a [[state]] $S_{t+1}$ when taking [[action]] a at the [[state]] s.
$$ p(s', r | s, a) = Pr(S_{t+1}=s', R_{t+1}=r| S_t = s, A_t=a) $$MDPs are the standard mathematical model for sequential decision making under uncertainty.
2. [[Solving a MDP]]:
	1. Fundamental Problems
	2. [[Bellman Equations]]

