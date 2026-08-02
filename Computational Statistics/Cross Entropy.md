This is the most used loss function for [[Classification]]. This gives the difference between 2 distributions.

$$
\textit{l}(\textbf{x, t, w}) = -\sum_{j}t_j log(p(c_j|x))
$$
where $$ p(c_j=1|x) = \frac{e^{y_j}}{\sum_{k=1}^{C}e^{y_k}} $$and t is the [[One-Hot Encoding]] output.