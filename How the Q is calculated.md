The universal template for change is $$ Q_{n+1} = Q_n + \alpha(R_n - Q_n) $$$$ new = old + \alpha(target-old) $$The alpha changes from approach to approach. 
- When $\alpha == 1/n$ then it is called the sample average.
- When $\alpha$ is constant, then the newer rewards are given more importance and the older rewards are $*\alpha^t$ so vanishes eventually.
## Sample Averages

- Let $N_t(a)$ = number of times action a has been selected before time t
- A natural estimate of potential rewards is the empirical mean of the rewards from the action $$Q_t(a) = \frac{\sum_{i=1}^{t-1}R_i*1}{\sum_{i=1}^{t-1}1} = \frac{1}{N_t(a) }\sum_{A_i=a}R_i $$
- The update function would look like $$ Q_{n+1} = Q_n + \frac{1}{n}(R_n - Q_n) $$ Which means that the Q of the next step is getting updated from the previous estimation by the value that is going towards the [[Reward]] got. new = old + $\alpha$(target-old) 
- This Q will always converge to the real value $Q^*$ when we are going for [[Stationary Reinforcement Learning]] problem.
- The action $A_t$ chosen according to $Q_t$. 