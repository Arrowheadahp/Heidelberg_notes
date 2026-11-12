Replace each pixel by a linear combination of its neighbours and itself
![[Pasted image 20260506000307.png]]

### [[Properties of Convolution]]
Linear, Associative, Commutative, Can be written as a matrix.
Convolution decreases the size of the image which can be counteracted by [[Padding]]

### Filters
![[List of Convolution Filters]]

### [[Computation of Convolutions]]

 
>[!note] Convolution can also sharpen an image as well by amplifying what "smoothing can remove"
$$ F_{sharp}=F+\gamma(F-h_{blur}*F)$$
