## Principal Component Analysis
The idea is to rotate the axis in the direction of maximum variance.
$V^*:=\arg\max_V(Var(X))$ with constraint $||V||=1$
Using [[Lagrange Multiplier]], 
The becomes: $$\mathcal L = V^TSV-\lambda(V^TV-1) $$
Where S is the [[Covariance matrix]] of X.
Maximising this Function gives $$(S-\lambda I)V =0$$
This comes down to [[Eigen Value]]. Since S is symmetric and real due to it being the [[Covariance matrix]], so the [[Eigen vectors]] are orthogonal and values real.

If we sort the [[Eigen vectors]] according to values, then we order by explained variances.