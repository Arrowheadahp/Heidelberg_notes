### Definition
When the [[Camera Calibration Matrix K]] is not known for any of the 2 views, then the total transformation that happens to get $x_1$ from $x_0$ is called the [[Fundamental Matrix F]].
### Derivation
![[Pasted image 20260810010026.png|500]]

When all 3 vectors lie on a plane, $a\cdot(b\times c) = 0$   
The 3 vectors are:
1. Translation change: $T=C_1 - C_0$
2. Inverse projection of image of $X$ from camera 1: $X - C_0 = K_0^{-1}x_0$ 
   since $x_0=K_0(X-C_0)$ 
3. Inverse projection of image of $X$ from camera 2: $X - C_1 = RK_1^{-1}x_1$ 
   Here $R$ is the Rotation change from camera 1 to camera 0

The equation comes as: $$ (X-C_0)^T(C_1-C_0) (X-C_1) =0
$$
$$x_0^TK_0^{-T}[C_1-C_0]RK_1^{-1}x_1 = 0
$$
Here, $K_0^{-T}[C_1-C_0]RK_1^{-1}$ becomes F (Fundamental Matrix) when the $K^{-1}$ are not known and becomes [[Essential Matrix E]] when they are known. $$ F = K_0^{-T}[C_1-C_0]RK_1^{-1}$$
