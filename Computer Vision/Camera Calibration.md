Knowing points $X_1, X_2 ...$ and the points in real life where they end up in the image $x_1, x_2, ...$ we can find out what the [[Camera Matrix P]] is with the equation $\lambda x = PX$. 

P has 11 degrees of freedom, so it has 12 unknowns and therefore require 12 equations. each point pair $(X,x)$ gives 3 equations but only 2 linear independence after removing $\lambda$ by taking ratios.
Therefore we need at least ==6 points== to get the 12 equations where we perform [[Solving Homogenous Linear Systems]] to get the P.

![[Pasted image 20260808170812.png]]
![[Pasted image 20260808170831.png]]
Many things can be done with extrinsically (C, R) calibrated and Intrinsically (K) calibrated camera like robot navigation, augmented reality, stereo cameras etc. 

### Can we get K,R,C from P:
Since K has 5 DOF, 
R has 3 DOF
C has 3 DOF, 
Total becomes 11, same as P
It can be done.