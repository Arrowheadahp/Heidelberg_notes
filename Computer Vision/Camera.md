## Camera vs human perception:
  Humans have very high resolution at the fovea and uses cone cells for colour measurement which only detects red, green and blue. Rod cells are for detecting brightness. Camera uses pixels arranged in certain way. and needs to be 'demosaiced'
## [[Pinhole Camera]] 
### [[Camera Calibration Matrix]]
The Final Calibration Matrix $K$ is: $$K=\begin{bmatrix}
f & sf & p_x+sp_y \\
0 & mf & mp_y \\
0 & 0 & 1
\end{bmatrix}$$
### [[Camera Matrix]]
![[Camera Matrix]]
## [[Lens Effects]]
### Solving Homogenous Linear Systems
  [[SVD]]
### Camera Calibration
Knowing points $X_1, X_2 ...$ and the points in real life where they end up in the image $x_1, x_2, ...$ we can find out what the camera matrix P is with the equation $\lambda x = PX$. Since P has 11 degrees of freedom, it has 12 unknowns and requires 12 equations and therefore 6 real points.
$$ x = KR(C-C~)X $$
Many things can be done with extrinsically (C, R) calibrated and Intrinsically (K) calibrated camera like robot navigation, augmented reality, stereo cameras etc. 