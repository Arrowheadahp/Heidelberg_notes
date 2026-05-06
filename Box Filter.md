For the purpose of [[Noise Removal]], If the noise added follows [[Gaussian Distribution]], it can be derived that the best filter to get the true value is a [[Box Filter]]

$$ \frac{1}{9}\begin{bmatrix}1 & 1 & 1 \\1 & 1 & 1 \\1 & 1 & 1 \\\end{bmatrix} $$
### Proof of box filter as optimal under gaussian noise

Since the noise is [[Gaussian Distribution]]:
$$ p(x_r|y_r)=N(x_r;y_r,\sigma) \sim e^{-\frac{(x_r-y_r)^2}{2\sigma^2}} $$
$y_r$ is real value
$x_r$ is observed value
$$ p(y_r|x_r) = \frac{p(x_r|y_r)*p(y_r)}{p(x_r)}
$$

Assuming $p(y)$ and $p(x)$ are constants
$$ p(y|x) = p(x|y) \sim \prod_{r}\prod_{r^`\in W(r)}{e^{-\frac{(x_{r^`}-y_r)^2}{2\sigma^2}}} 
$$
W is the small vicinity, r is each pixel
$$ y^* = argmax_y (p(y|x)) $$
For single pixel,
$$ log(y^*) = -\frac{1}{2\sigma^2}\sum_{r^`\in W(r)}{(x_{r^`}-y_r)^2}
$$
$$\frac{dF}{dy_r} = \sum_{r^` \in W}{2*(x_{r^`}-y_r)*-1=0}
$$
$$y_r = \frac{1}{|W|}\sum_{r^`}{x_{r^`}}
$$Trivial solution
### Method for faster computation:

Create a sum table 
$$S_{i,j}= \sum_{u=0}^{i}\sum_{v=0}^{j}P_{u,v}
$$
```
S[i][j] = S[i-1][j]+S[i][j-1]-S[i-1][j-1]+P[i][j]
```
So the convoluted value would be
```
C[i][j] = S[i+1][j+1]-S[i-1][j+1]-S[i+1][j-1]+S[i-1][j-1]
```



