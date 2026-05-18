
> [!Question] Guiding Question
> If the model is known, how can we compute optimal behaviour without trial and error learning?

Dynamic Programming computes value functions and optimal policies by turning [[Bellman Equations]] into repeated update rules in [[Stationary Reinforcement Learning]].
### Cons:
- Dynamic Programming is often impractical since it requires a known model  which in turn many sweeps through the state space. Perfect model means that the [[State Value Function]] and the [[Action Value Function]] are known already. 
- Many RL algorithms can achieve the same effect without the perfect model and therefore less computation since there can be [[State]] that are very rare. 
### Pros:
-  It gives a conceptual template for prediction, Improvement and control.

> [!Intuition] 3 parts
> [[Policy Evaluation]]: Estimating how good a [[State]] is.
> [[Policy Improvement]]: Choosing better [[Action]] using those values
> [[Policy Iteration]]: Repeat alternating above 2 until minimal changes.

The main difference between the [[Monte-Carlo Simulations]] and the [[Dynamic Programming in RL]] is that since the models is known, DP can compute the expectations exactly. But for that it has to be finite [[Markov Decision Processes]]. Meaning, the number of states, and action are finite.
