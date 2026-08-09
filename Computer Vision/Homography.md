### Definition
Projectivity or homography is an invertible mapping h from $P^2$ to $P^2$ such that any 3 points that lie on the line also lies on a line in [[Projective Geometry]]. ==A mapping H is homography iff there exists a non-singular 3x3 matrix H with $x'=Hx$.==

When the camera is rotated and still shows the same objects or the object is revolves around the camera for a few degrees, we can calculate the transformation using Homography. 
### Derivation
Here K is the [[Camera Calibration Matrix K]].
Since the 3d object remains the same, camera 0 gets the image: $x_0=K_0X$
and the Camera 1 gets the image: $x_1=K_1RX=K_1RK_0^{-1}x_0 = Hx_0$
Therefore $$H=K_1RK_0^{-1}$$
> [!NOTE] Homography has 8 degrees of freedom
### Computation
When we have 2 images, we have 2 lists of matching points: $x'$ and $x$. After adjusting for brightness changes$(\lambda)$, the equation becomes $$\lambda x' = Hx$$
For each matching point ($x,x'$), we get 3 equations with $\lambda$ and after removing $\lambda$, we get 2 equations just like [[Camera Calibration]] and we solve it the similar way using [[Solving Homogenous Linear Systems]]. Since ==there are 8 degrees of freedom, we have 8 variables, therefore we need 8 equations which require 4 matching points==. So with 4 point matches, we can solve for H. So the pipeline becomes:

1. take $m\geq4$ point matches from the 2 images  ($x,x'$)
2. Normalize the values using T.
3. Assemble A which satisfies $Ah=0$
4. Compute $h* = \arg \min_h ||Ah||_2$ subject to $||h||_2 = 1$. This is done by [[Solving Homogenous Linear Systems]].

> [!NOTE] We can only get the $K_1, R$ and $K_0$ from the equation $H=K_1RK_0$ of a rotating camera with lots of assumptions for K since the degrees of freedom for H is 8 and for RHS is 13
### Applications
We can use H to get to stitch multiple images to make panoramas.
We can use this for document scanning.
It is used for showing ads on planar surfaces

### [[Accurate Geometry estimation for 2 views]] has the final algorithms for estimating H using [[RANSAC]].