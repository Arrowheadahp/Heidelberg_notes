
> [!Quote] If we select on x axis the function value of the data term and on the y axis that of the regularization term, ten varying the $\lambda$ generates an L- shaped curve

### Construction:
1. Plot the log-log plot of the data term and the regularization term
2. Vary $\lambda$ to get the curve
3. Plot the maximal curvature of the $\lambda^*=\arg\max c''(\lambda)$ 


> [!NOTE] [[L-Curve]] is purely empirical method that often leads to usable solution but far from the true optimum
> Contents


![[Pasted image 20260922203832.png|512]]

#### Pros: 
1. [[L-Curve]] is simple to implement
#### Cons:
1. It is expensive to compute the samples and then then use fitting strategies like [[splines]].
2. We may not see an L shape and the curvature may be the same everywhere
3. The method does not use statistical information