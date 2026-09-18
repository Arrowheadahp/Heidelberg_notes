[[Data Resolution Matrix (N)]] and [[Model Resolution Matrix (R)]] are perfect when they are diagonal. So we can get a measure of how good the $A^{PI}$ is by the spread of $N$.

Spread(B) is the 2-norm of ($B-I$) = $||B- \mathbb I||^2_2$

We use this spread function to calculate the [[Loss Function]] $J$ and then calculate  $\arg\min_{A^{-1}}J$ by $$\frac{\delta J}{\delta A^{-1}}\gets0$$