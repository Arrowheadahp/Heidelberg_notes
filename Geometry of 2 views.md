### Part 1: When the camera is only rotated and not moved

[[Homography]]: Projectivity or homography is an invertible mapping h from $P^2$ to $P^2$ such that any 3 points that lie on the line also lies on a line in [[Projective Geometry]]. A mapping H is homography iff there exists a non-singular 3x3 matrix H with $x'=Hx$.

This happens when the camera is rotated to take pictures of the same thing from different angles.

When we have 2 images, we have 2 lists of matching points: $x'$ and $x$. After adjusting for brightness changes$(\lambda)$, the equation becomes $$\lambda x' = Hx$$
1. take $m\geq4$ point matches from the 2 images
2. Assemble A which satisfies $Ah=0$
3. Compute $h* = \arg \min_h ||Ah||_2$ subject to $||h||_2 = 1$. This is done by [[SVD]]

### Part 2: When the camera is rotated and moved:

[[Fundamental/Essential Matrix]]: With more than 7 matching points, we can make a matrix that can encapsulates the transformation that happens when the camera is moved from 1 place to another.

The basic idea is that in 3d [[Projective Geometry]], each matching point pair makes a plane with the camera centres.