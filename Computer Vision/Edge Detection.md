
Edges can be shown by getting the 1st derivative of the picture after convolution so as to not detect noise.$$ \frac{d}{dx}(g*f) = (\frac{d}{dx}g)*f
$$
But Because $dx$ is 1 pixel, the derivative becomes $$ f(x+1)-f(x) $$
![[Pasted image 20260506031210.png|500]]

[[Sobel Filter]] is used for this purpose along with the [[Gaussian Filter]].

### [[2D Gradient]]
![[2D Gradient]]