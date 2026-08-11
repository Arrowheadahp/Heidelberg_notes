## Bidirectional Reflectance Distributed Function
BRDF has to follow 2 rules
1. [[Helmholtz Reciprocity]] 
2. Energy Conservation

This consists parts from reflection:
1. [[Diffusion]] which depends on the colour of the object c also called 
2. [[Specular Reflection]] which 
### Cook Torrance BRDF
 $$f_r(\omega_i, \omega_o) = (1-F).c + \frac{D.F.G}{4(\omega_i.n)(\omega_o.n)} $$
D is the models distribution of microfacets
$$ D=\frac{1}{\pi\alpha^2}(n\cdot h)^{\frac{2}{\alpha^2}-2}$$
$\alpha$ is the roughness $\alpha\in[0,1]$
h  is the halfway line between the $\omega_o$ and $\omega_i$.
n is the normal
c is the colour of the point (albedo)
F is the Fresnel Function (Specular Strength depends on viewing angle)
G is the Geometric Attenuation Function

### Metals
Metals absorb or re-emit all light at its surface. So there is no Diffusion but the [[Specular Reflection]] takes the colour of the metal. Nearly all surfaces are either fully metallic or fully non metallic.
### Relevant terms
Artists only care about 3 things to describe a surface:
1. Colour
2. Metallicity
3. Roughness