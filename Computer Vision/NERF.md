Neural Radiance Fields
- The [[Neural Network]] maps from 3D location and view direction to color and density
- We train one [[Neural Network]] for all 3D locations of a static scene.
- Density $\sigma$ describes how solid/transparent a 3D point is (eg. fog)
- Conditioning on Viewing direction allows for a modelling view-dependent effects
- In practice, the view direction is input as normalised 3D vector d
### Volume Rendering
Rendering model for ray: $$ C= \sum_{i=1}^N T_i\alpha_i c_i$$
c = colours
T = Weights$$ T_i = \prod_{j=1}^{i-1}(1-\alpha_j)$$
$\alpha$ = opacity or how much light is contributed by ray segment i 
$$\alpha_i = 1-e^{-\sigma_i \delta t_i}$$

### Training
The models are trained by
1. Shoot ray
2. Samples 3D points on the ray
3. predict color and density with F
4. re-render ray pixel with volume rendering
5. minimize reconstruction error by backpropagation

### Positional Encoding
This results in sharper, more detailed images and has faster convergence
Instead of the NN memorizing pixel by pixel it memorizes Fourier features using [[Fourier Cosine Basis]].
![[Pasted image 20260623145855.png]]

### Results:
NERF models show view dependent effects
View dependency can be visualized by querying color of the same pixels for different viewing angles.
Can be used for depth derivation, image stabilizing