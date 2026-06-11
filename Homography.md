Projectivity or homography is an invertible mapping h from $P^2$ to $P^2$ such that any 3 points that lie on the line also lies on a line in [[Projective Geometry]]. A mapping H is homography iff there exists a non-singular 3x3 matrix H with $x'=Hx$.

This happens when the camera is rotated to take pictures of the same thing from different angles.

When we have 2 images, we have 2 lists of matching points: $x'$ and $x$. After adjusting for brightness changes$(\lambda)$, the equation becomes $$\lambda x' = Hx$$
expanding and removing the lambda from the equation gives 2 equations per 1 point match. so with 4 point matches, we can solve for H. So the pipeline becomes:

1. take $m\geq4$ point matches from the 2 images
2. Assemble A which satisfies $Ah=0$
3. Compute $h* = \arg \min_h ||Ah||_2$ subject to $||h||_2 = 1$. This is done by [[SVD]]


> [!NOTE] We can only get the $K_1, R$ and $K_0$ from the equation $H=K_1RK_0$ of a rotating camera with lots of assumptions for K since the degrees of freedom for H is 8 and for RHS is 13

We can use H to get to stitch multiple images to make panoramas