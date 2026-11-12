Forward pass is for calculating the p(c)

$$ x\to h_1 = max(0, w_1x+b_1) \to y = max(0, w_2x+b_2)\to p(c_i) = \frac{exp(y_i)}{\sum_{k}exp(y_k)} $$

We want *dl/dw2* and *dl/db2* are necessary for the W2 and b2. *dl/dh1* is needed for w1 and b1


[[Example Gradient descent for loss function Cross Entropy]] 