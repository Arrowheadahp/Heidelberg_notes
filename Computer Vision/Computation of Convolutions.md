There are multiple ways of computing convolutions
### For [[Convolutional Neural Networks]]
1. Explicit computation (complicated for special cases ex: Padding)
2. [[Convolution using Fourier Transform]]: (complicated for special cases ex: Padding)
3. Best: 
   Fastest way to compute is to have a matrix vector product: $B*I=R$
   Where B is band matrix, ==I is vector with image==, R is resulting image vector. This is the best for GPU

### For the [[List of Convolution Filters]]
The filters are separable, we can use the Associative [[Properties of Convolution]] for decomposing the filter into 1d vectors. This is possible for all [[List of Convolution Filters]] like ![[List of Convolution Filters]]