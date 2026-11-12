
> [!Question] How good is the policy $\pi$
> This calculates the $v_\pi$ and $q_\pi$ for a given $\pi$ keeping policy remains unchanged.

Policy Evaluation is finding the [[State Value]] ($v_\pi$) and the [[Action Value]] ($q_\pi$).  for a particular [[Policy]] $\pi$.

For [[Markov Decision Process]], [[Bellman Equations]] are. 
Bellman Expectation Equation for $v_\pi$
$$
v_\pi(s) = \sum_a \left(\pi(a|s) \sum_{s',r}p(s',r|s,a)\left[r+\gamma v_\pi(s')\right] \right)
$$
The expected [[Return]] for [[State]] s is the summation of choosing [[Action]] a given s multiplied with the summation of multiplication of probability of getting next state s' and reward r plus gamma \* expected return at state s'.

There are 2 ways to do the [[Policy Evaluation]] to get the $v_\pi$.

1. [[Iterative Bellman Expectation Update]] 
2. [[Solving Linear System to evaluate policy]]

This is a way to solve the [[Bellman Equations]] but the [[Iterative Bellman Expectation Update]] is preferred because
1. the calculations are $O(s^3)$ 
2. the transition matrix P gets typically very large and sparse. 
3. Policies change repeatedly
4. [[Iterative Bellman Expectation Update]] generalizes better to other methods.