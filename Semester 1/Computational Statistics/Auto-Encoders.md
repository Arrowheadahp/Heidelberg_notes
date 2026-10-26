This uses [[Neural Network]] to compress or encode an image or other vectors into less number of dimensions and trains with the loss from the starting value called Reconstruction loss. 
The encoder reduces the dimensions and the decoder brings it back.

![[Pasted image 20260812135140.png|720]]

Loss Function: $$L=\mathbb E||x-D(E(x)) ||_2^2 $$
### Applications
1. [[Dimensionality Reduction]]
2. [[Image Generation]]
	   Here [[Variational Auto Encoder (VAE)]] is used
	