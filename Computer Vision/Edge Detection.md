
Edges can be shown by getting the 1st derivative of the picture after convolution so as to not detect noise.$$ \frac{d}{dx}(g*f) = (\frac{d}{dx}g)*f
$$
But Because $dx$ is 1 pixel, the derivative becomes $$ f(x+1)-f(x) $$
![[Pasted image 20260506031210.png|500]]

[[Sobel Filter]] is used for this purpose along with the [[Gaussian Filter]].

### 2D Gradient
This is a matrix of $$\nabla I=(I_x,I_y)=\left(\frac{\delta I}{\delta x},\frac{\delta I}{\delta y}\right)$$
The magnitude is $||\nabla I||=\sqrt{I_x^2+I_y^2}$
and the angle is $\theta=\tan^{-1}(I_y/I_x)$