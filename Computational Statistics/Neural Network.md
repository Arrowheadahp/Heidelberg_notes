This is multiple [[Perceptron]] working one after the other on each other's outputs. This is also known as multi-layer perceptron, Feed Forward Neural Network, [[Deep Neural Networks]], etc. 

[[Universal Update Template]] says that any boundary or function in n dimensions can be approximated with finite number of hyperplanes, the neurons are trying to simulate those hyperplanes. So with enough neurons, any decision boundary or any function can be approximated.

The [[Perceptron]]s are layered one by one and the layers between the input layer and the output layer are called hidden layers. Each [[Perceptron]] ends in an [[Activation Functions]], which has to non-linear otherwise the whole network becomes linear. In practice ==Batch Normalization== is also added between layers.

The optimal parameters can be found by minimising the [[Loss Function]] using [[Backpropagation]]. 

To avoid the [[Overfitting]], there are different options for ![[Generalization]]


