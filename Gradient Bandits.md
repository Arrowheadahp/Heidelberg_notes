Instead of choosing the [[Action]] directly, we can create a [[Policy]] of choosing action and improve it directly using gradients.
$$ \pi_t(a) = Pr(A_t=a)=\frac{e^{H_t(a)}}{\sum_{b=1}^{k}e^{H_t(b)}}
$$
Probability of choosing a: $\pi_t(a) = Pr(A_t=a)$ is equal to the [[SoftMax Function]] of the priority function $H_t(a)$. 

The idea is to change the values of H to maximise the expected Reward $J$. 
$$ J= \sum_{a=1}^k \pi(a)q^*(a)
$$
H is changed according to $$ H(a)=H(a)+\alpha\frac{\delta J}{\delta H}
$$$$ \frac{\delta J}{\delta H(a)} = q^*(a)(1\{A=a\} - \pi(a))
$$
We replace $q^*(a) = R_t$ and remove baseline from it to reduce variance. It does not change the expected gradient direction.
$$  \frac{\delta J}{\delta H(a)} = (R_t-\overline R_t)(1\{A=a\} - \pi(a)) $$
For selecting [[Action]] a, H(a) is changed as 
$$ H(a)=H(a)+\alpha(R_t-\overline R_t)(1\{A=a\} - \pi(a))
$$