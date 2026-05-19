- ## Camera vs human perception:
  Humans have very high resolution at the fovea and uses cone cells for colour measurement which only detects red, green and blue. Rod cells are for detecting brightness. Camera uses pixels arranged in certain way. and needs to be 'demosaiced'
- ## Pin hole camera 
  Add barrier to block most of the rays. .35 mm best. [[Projective Geometry]]. $$ x = PX $$
  Intrinsic Parameters:
	- Principal Point Coordinates $(p_x, p_y)$.
	- Focal length f
	- Pixel y-direction magnification factors m
	- skew s
	Extrinsic Parameters:
	- Rotation R and translation C
- ## Lens Effects
	- larger aperture causes blurry images
	- smaller aperture causes diffraction
	- lens allows more light . It allows objects at a certain distance to be in focus.
	- shorter aperture causes more depth of field but lets in less light
	- closer images causes large fov, farther images causes low fov
	- chromatic aberrations are caused by different wavelengths of light being bent differently by the lens
	- Vignetting is caused when there is a second lens which does not capture all of the light from the first lens
	- lens distortion is caused by fish eye cameras
- ## Solving Homogenous Linear Systems
  [[Singular Value Decomposition]]
- ## Camera Calibration
  Knowing points $X_1, X_2 ...$ and the points in real life where they end up in the image $x_1, x_2, ...$ we can find out what the camera matrix P is with the equation $\lambda x = PX$. Since P has 11 degrees of freedom, it has 12 unknowns and requires 12 equations and therefore 6 real points.
$$ x = KR(C-C~)X $$
	Many things can be done with extrinsically (C, R) calibrated and Intrinsically (K) calibrated camera like robot navigation, augmented reality, stereo cameras etc. 