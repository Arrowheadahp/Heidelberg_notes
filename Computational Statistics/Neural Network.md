This is multiple [[Perceptron]] working one after the other on each other's outputs. This is also known as multi-layer perceptron. It is also called "Feed Forward Neural Network"

The [[Activation Functions]] make it better. Otherwise it would essentially become a [[Linear Model]].

Any boundary or function in n dimensions can be approximated with finite number of hyperplanes, the neurons are trying to simulate those hyperplanes. So with enough neurons, any decision boundary or any function can be approximated.

[[Probability Rules]]
[[Derivative Rules]]

[[^Chain Rule]] is more important for the back propagation

- Encode output with 1-k encoding: \[0, 0, 1, 0]
- Define a [[Loss Function]] *L*(w)
- Find the optimal parameters that minimizes the [[Loss Function]].
  $$ \textbf{w}^* = argmin(\textit{L}(\textbf{w})) $$



The optimal parameters can be found by minimising the [[Loss Function]] using [[Gradient Descent]]. 

To avoid the [[Overfitting]], there are different options for [[Generalization]]:


