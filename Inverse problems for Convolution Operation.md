[[Properties of Convolution]] states that Convolution is a [[Linear System]]. 

As an example of inversing a convolution operation we look at deblurring.
Blurring occurs due to motion blur, out of focus, physical resolution being smaller than object.
### What is convolution:
$$(f\otimes g)(j)=\sum_{i=-N}^Nf_{j-i}g_i$$
Deblurring require calculating the inverse of the [[Point Spread Function]] which is a convolution operation.

For the operation of convolution and the inverse of it, we use the Convolution using [[Fourier Transform]] since the convolution operation becomes a multiplication after Fourier transform. This is the meaning behind [[Convolution Theorem]] which gives the [[OTF]]. 

For the purpose of inversion using [[Convolution Theorem]], we divide the G with [[OTF]]. But there are problems with dividing with the OTG.
$$ g=PSF\otimes f+\varepsilon$$
$$G=OTF\cdot F+E$$
$$F = \frac{G-E}{OTF}$$
### [[Problems with Naive solution of Inverse Problems]]
