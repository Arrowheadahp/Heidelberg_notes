In the forward pass of the true parameters, the observed data is obtained
$$g_{obs}=Af_{true}+\varepsilon$$
We use the observed data to obtain the estimated parameters $$f_{est}=A^{inv}g_{obs}$$
We can use the estimated parameters to get the ==predicted data== $$g_{pre}=Af_{est}$$
The ==predicted noise== or prediction error is the difference between predicted data and the observed data.
$$\varepsilon = g_{obs}-g_{pre}$$
[[Pseudoinverse]] solution to getting the estimated parameters aims to minimise the sum of squared predicted noise.