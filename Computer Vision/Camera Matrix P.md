The Equation for camera matrix is $$x=KR(I-\tilde C)X=PX $$
Here The Camera Matrix is  $P=KR(I-C)$ 
Intrinsic Parameters: [[Camera Calibration Matrix K]] is$$K=\begin{bmatrix}
f & sf & p_x+sp_y \\
0 & mf & mp_y \\
0 & 0 & 1
\end{bmatrix}$$
- $p_x,p_y$ are the centre of the image or the principal point of the image.
- $f$ is the focal point
- $m$ is the magnification factor in the $y$ direction
- $s$ is the skew because of non-rectangular matrix.
Extrinsic Parameters:
- Rotation R and translation C
#### Finding the value of P is done by [[Camera Calibration]].

> [!NOTE] P has 11 degrees of freedom