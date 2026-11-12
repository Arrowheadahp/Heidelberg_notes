This is the function that dictates how the incident ray $\omega_i$ at point $p$ is transformed when being turned into emitted ray $\omega_e$.
$$f_r(p, \omega_i \to \omega_o)$$
Bidirectional Reflectance Distributed Function ([[BRDF]]) is a subset of Bidirectional Scattering Distributed Function (BSDF).

BSDF consists of 
1. [[BRDF]]
	1. [[Diffusion]]
	2. [[Specular Reflection]]
2. Subsurface scattering
3. Volumetric Scattering
4. Particle Effects
5. Refractions 
etc

BRDF has to follow 2 rules: 
1. Helmholtz reciprocity $f_r(p, \omega_i \to \omega_o) = f_r(p, \omega_o \to \omega_i)$
2. Energy conservation

