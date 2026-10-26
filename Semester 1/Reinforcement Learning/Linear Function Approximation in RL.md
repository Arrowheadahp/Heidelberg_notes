Here the $x(s)$ is the features of the state (using [[Feature Construction for Linear Methods]] ) and w is the linear weights trained by $$w_{t+1}=w_t + \alpha \left[ U_t - w^T_tx_t \right]x_t $$because $$\nabla_w\hat v(s, w) = x(s) $$It is guaranteed to converge even with [[On-Policy]] [[Temporal Difference Learning]].

The error is bounded $$ VE(w_{TD}) \le \frac{1}{1-\gamma} \min_w (VE(w)) $$
![[Pasted image 20260626193621.png]]