Rendering is the graphics based image generation.

### Rendering Equation: 
$$ L_o(p, \omega_o) = L_e(p, w_o)+\int_H f_r(p, \omega_i \to \omega_o)L_i(p, \omega_i) \cos \theta\ d\omega_i $$
$L_o(p, \omega_o)\to$ Outgoing light at point p in the direction of $\omega_o$
$L_e(p, \omega_o)\to$ Emitted light at point p in the direction of $\omega_o$
$L_i(p, \omega_i)\to$ Incident light at point p from the direction of $\omega_i$
$f_r(p, \omega_i \to \omega_o)\to$ [[Scattering function]] at point p. Defines how light is reflected by a specific material

p in the point in 3D space
H is all directions in the hemisphere
$\theta$ is the angle between incident ray and normal

> [!NOTE] Solving the Equation
> Instead of shooting rays from the light source, we shoot rays from the camera and approximate the pixel colour from the multiple rays using Monte Carlo Simulations.
