https://www.youtube.com/watch?v=vSczTbgc8Rc

Any matrix can be decomposed into 3 parts
$$ A = UDV^T$$
- Where U is an orthogonal matrix that does a rotation. It is the normalized eigen vectors of $S_L = AA^T$ arranging in descending order.
- D is the rectangularly diagonal matrix that does stretching. It is composed of $\sigma_i$ where they are the singular values, also the eigen values of $A^TA$ sorted in descending order.
- Where U is an orthogonal matrix that does a rotation. It is the normalized eigen vectors of $S_R = A^TA$ arranging in descending order. Since we multiply $V^T$ so we are rotating the opposite way of $V$ since transpose of an orthogonal matrix is its inverse.

So when we are transforming by $A$ means that we are sequentially doing 
1. $V^T$ first meaning rotating the opposite way of the eigen vectors.
2. $D = [\sigma_i]  I_{mxn}$ = So it stretches and removes/ adds dimension to become same dimension as A.
3. $U$ is another rotation in the correct way.

Eigen Vector:
Eigen vector of a matrix is the vector of unit length that does not change in direction after being transformed by the matrix. $$ A\vec v = \lambda \vec v $$ $\lambda$ is the Eigen value.

Definition of Orthogonal matrices is that the column vectors of the matrix are unit and perpendicular. So Eigen vectors combined column-wise makes an orthogonal vector. 
Because the column vectors of the matrix are unit and perpendicular, orthogonal matrices perform only rotation.