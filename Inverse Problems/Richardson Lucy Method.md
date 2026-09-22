This is an iterative approach that is done by Expectation Maximisation of the [[Poisson Distribution]]. 
The iteration is 
$$f_j^{new} = \frac{f_j^{old}}{\sum_{i=1}^nA_{ij}}\sum_{i=1}^mA_{ij}\frac{g_{i}}{\sum_{k=1}^nA_{ik}f_k^{old}} $$
This is a superior iterative approach than [[Landweber Method]] for 3 reasons
1. This is a multiplicative approach, so it has the condition $f\ge0$ baked in. [[Landweber Method]] had to use [[POCS]] for this
2. This uses the maximum estimation approach of Poisson Distribution instead of [[Landweber Method]] using the generic least squares method.
3. This converges faster

For the Regularized method:$$f_j^{new} = \frac{f_j^{old}}{\sum_{i=1}^nA_{ij}+\frac{\partial D(f^{old})}{\partial f_j}}\sum_{i=1}^mA_{ij}\frac{g_{i}}{\sum_{k=1}^nA_{ik}f_k^{old}} $$

