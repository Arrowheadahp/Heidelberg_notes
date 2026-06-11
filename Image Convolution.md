Replace each pixel by a linear combination of its neighbours and itself
![[Pasted image 20260506000307.png]]

[[Properties of Convolution]]
Linear, Associative, Commutative, Can be written as a matrix


Filters
1. [[Box Filter]] is a filter (also called kernel) that helps in blurring and [[Noise Removal]]
2. [[Sobel Filter]] can be used for [[Edge Detection and Linking]]
3. etc


> [!NOTE] Applications
> [[Noise Removal]]


>[!Note] Computation
> Fastest way to compute is to have a matrix vector product: $B*I=R$
  >>Where B is band matrix, I is vector with image, R is resulting image vector
  >This is the best for GPU
 
