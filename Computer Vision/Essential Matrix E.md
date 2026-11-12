When the [[Camera Calibration Matrix K]] is known for 2 views, then we only need the translation and the rotation part of the transformation. 
$$ x_0^T\tilde TRx_1=0$$ $$E=\tilde TR$$
### Derivation
The derivation is same as [[Fundamental Matrix F]] but the Ks are known. E is of rank 2, same as F but it as 5 degrees of freedom since T has 3 and R has 3.

### Computation
The algorithm is exactly same as that of computing F. It can be done with 8,7,5 points.

Can we compute T and R?
Since combined T and R has 5 degrees of freedom, and E has 5 degrees of freedom, yes.
We do this by decomposing E into UDV by [[SVD]] 
R has 4 possible solutions: 
![[Pasted image 20260810131633.png|512]]

Reconstruct a 3D point and choose the solution where it lies in front of the 2 cameras. Therefore 1 solution is valid.
