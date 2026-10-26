
Derivative of loss wrt output for [[Loss Function#^cross]]:
- $$ \textit{l}(x, t, w) = -\sum_{j} t_j log (p(c_j|x)) $$
- $$ p(c_j=1|x) = \frac{e^{y_j}}{\sum_{k=1}^{C}e^{y_k}} $$
- $$ \frac{\delta\it{l}}{\delta y} = o(c|x) - t $$
	- t is the true label
	- p(c) = the predicted label
