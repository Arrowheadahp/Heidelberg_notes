
> [!Question] How can we follow the gradient of expected return with respect to policy parameters, even though the distribution itself depends on the policy?

Instead of using [[Function Approximation in RL]] to estimate $q(s,a)$, and then calculating the policy $\pi(s)=\arg \max_a(q(s,a))$, we are approximating the policy directly. $$\pi(s,\theta)= \Pr\{A_t=a|S_t=s, \theta_t=\theta\} $$
Just like the [[Gradient Bandits]], we are using [[SoftMax Function]] to calculate the probability.
$$\pi(s,\theta)= \frac{e^{h(s,a, \theta)}}{\sum_{b=1}^{k}e^{h(s,b, \theta)}} $$
The $\hat v(s, w)$ is still necessary to learn theta but it is not required anymore for action selection.

#### Advantages of Soft-max over $\varepsilon$:
1. Sometimes the best policy is probabilistic (ex: Bluffing in Poker)
2. Sometimes action preference $H$ is easier to learn than action value $q$.
3. Approach the optimum policy smoothly instead of [[Eta-greedy]] where greedy action changes discontinuously with tiny changes in $q$.
4. It can handle continuous action spaces.

### [[Policy Gradient Theorem]] 
states that for any differentiable policy $\pi(a|s,\theta)$,$$\nabla J(\theta)\propto \sum_s\mu(s)\sum_a q_\pi(s,a)\nabla\pi(a|s,\theta) $$
One of the model that utilizes this Policy gradient is [[REINFORCE]].








