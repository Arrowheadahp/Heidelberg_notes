This is the [[Covariance]] of the $f_{est}$ that is used in the [[Quality of Inverses]]. 

Let $$f_{est} = Mg_{obs}+v$$
Here M can be the [[Pseudoinverse]] for any [[Determinism]]. 
$$cov(f_{est}) = E[(f-E[f])(f-E[f])^T]==Mcov(g)M^T$$
For overdetermined case: $cov(f_{est}) = M\sigma^2M^T= \sigma^2(AA^T)^{-1}$
For underdetermined case: $cov(f_{est}) = M\sigma^2M^T= \sigma^2A^T(AA^T)^{-2}A$