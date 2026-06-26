Bidirectional Reflectance Distributed Function

This consists parts from reflection:
1. [[Diffusion]] which depends on the colour of the object
2. [[Specular Reflection]] which 
### Cook Torrance BRDF
 $$f_r(\omega_i, \omega_o) = (1-F).c + \frac{D.F.G}{4(\omega_i.n)\omega_o.n} $$
D is the models distribution of microfacets
F is the Fresnel Function (Specular Strength depends on viewing angle)
G is the Geometric Attenuation Function