The basic idea is that in 3d [[Projective Geometry]], each matching point pair makes a plane with the camera centres.

Because all 3 vectors lie on a plane, $a\cdot(b\times c) = 0$   
The 3 vectors are:
1. Translation change: $T=C_1 - C_0$
2. Inverse projection of image of $X$ from camera 1: $X - C_0 = K_0^{-1}x_0$ 
3. Inverse projection of image of $X$ from camera 2: $X - C_1 = RK_1^{-1}x_1$ 
   Here $R$ is the Rotation change.

The equation comes as: $$ (X-C_0)^T(C_1-C_0) \times (X-C_1) =0
$$
$$x_0^TK_0^{-T}[C_1-C_0]RK_1^{-1}x_1 = 0
$$
Here, $K_0^{-T}[C_1-C_0]RK_1^{-1}$ becomes F (Fundamental Matrix) when the $K^{-1}$ are not known and becomes Essential when they are known. $$ F = K_0^{-T}[C_1-C_0]RK_1^{-1}$$
### Epiploar Planes and Epipole

The epipolar line calculated from camera 1 of point $x_0$ as $$ l_1^Tx_1 = x_0^TFx_1$$
The epipolar line calculated from camera 0 of point $x_1$ as $$ x_0^Tl_1^T = x_0^TFx_1 $$
The epipole $e_0$ can be calculated as $$ e_0^TF = 0^T$$
### How to compute F (2 views)

8 point algorithm:
1. take $m\ge8$ points
2. Compute $T = C_1-C_0$ and condition points: $\bar x = Tx, \bar x' = T'x'$ 
3. Assemble A with $Af=0$. Here A is of size $m\times9$ and f vectorized F.
4. Compute $f* = \arg \min_f ||Af||_2$ subject to $||f||_2=1$. Use [[SVD]] for this.
5. Get F of unconditioned points: $T^TFT'$.
6. Make rank(F) = 2. This is done by making $\sigma_{p-1}=0$ of the $\Sigma$ of SVD.

7 point algorithm:
1. Take $m=7$ points
2. Assemble A with $Af=0$. Here A is of size $m\times9$ and f vectorized F.
3. Compute 2D right null space: $F_1, F_2$ from last 2 rows in $V^T$ from [[SVD]].
4. Choose $F=\alpha F_1 + (1-\alpha)F_2$
5. Determine $\alpha$ so that $det(F)=0$.


> [!NOTE] Auto Calibration
> Getting K, R, T from F is hard and is called auto calibration. It is only possible with external constraints. K, R, T have 15 degrees of freedom in total and F has 7.

![[Pasted image 20260615190450.png]]