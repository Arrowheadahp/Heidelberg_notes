$\varepsilon$ greedy do not care about the uncertainty of the each action and how many times it has already been taken. To counteract that, the action taken will be dictated by
$$A_t = \arg \max_a\left(Q_t(a)+c\sqrt{\frac{ln(t)}{N_t(a)}}\right)
$$
Here, 
- $t$ is the number of times any action has been taken from this this state
- $N_t$ is the number of times Action a has been taken
- c is the factor of how much the uncertainty will be prioritised.
- $c\sqrt{\frac{ln(t)}{N_t(a)}}$ is the uncertainty factor.
