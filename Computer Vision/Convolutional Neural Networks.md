## Convolution Layer
This is a way to analyse pictures by using multiple filters ([[Image Convolution]]) over the pixels. Example a 11\*11\*3\*100 is a 11\*11 convolution that is happening over 3 channels (RGB) and there are 100 of them. 
## Pooling Layer
This is to get the some value from its neighbouring "pixels". The most used one is the max pooling layer. This is so that the pixels where the filters give large values stay and the rest don't. others exist such as average pooling layer, etc.
### Flattening layer
This is to flatten the outputs to a vector to be added to a [[Neural Network]].
Convolution is Differentiable, so [[Backpropagation]] works on the weights of the convolution.

### In practice:
1. Use millions of training data
2. Enrich your training data with [[Data Augmentation]]
3. Cut off Fully connected layers and re-train them for other specific problems. ([[Pretext Task]])

Hyper parameters:
1. Size of filter: 3\*3 best
2. Size of padding: 1 if 3\*3 filter is used. This is so that the edge pixels are also used for the training
3. Strides: The number of pixels skipped after every [[Image Convolution]].
4. Number of filters
