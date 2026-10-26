This is another way to perform [[Edge Detection]] but instead of using [[2D Gradient]] with derivating once, we are derivating twice using the Laplacian operator. Combining it with the [[Gaussian Filter]], it becomes the [[Laplacian of Gaussian (LoG)]].

The Laplacian operator is $$\nabla^2I=\frac{\delta^2 I}{\delta x^2}+\frac{\delta^2 I}{\delta y^2} $$
The [[Laplacian of Gaussian (LoG)]] operator is $\nabla^2G$.