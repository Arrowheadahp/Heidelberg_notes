This is one of the applications of what we have been trying to do
### Problem Setting
This task is also called Structure from motion (SfM)
Given m cameras (images) and n is the number of 3D capture points. 
Formally $x_{ij}=P_jX_i$ where $j\in\set{1,...,m}$ and $i\in\set{1,...,n}$ and [[Camera Matrix P]].
But we don't have all the points visible in all images. $x_{ij}\le mn$
==So the goal is to find $P_j$ and $X_i$.==

### Reconstruction Algorithm
1. Compute accurate [[Fundamental Matrix F]] between one pair of neighbouring images
2. If uncalibrated, derive the [[Camera Matrix P]] by assuming s=0 and m=1 for the first pair of images. 
	We get the intrinsic from F and then get T and R from the resulting [[Essential Matrix E]].
3. Compute the initial reconstruction $X$ using the 2 points using the following calculations
	$x_0=K_0X$ and $x_1=K_1R^{-1}[I-T]X$
4. Successively add more images with interleaved bundle adjustment (while minimising geometric error, calibrate new view.
	1. Select a view with many putative matches wrt to the already reconstructed views
	2. Sample many focal lengths to get candidates for camera matrix K. s and m is guessed.
	3. [[RANSAC]]
		1. sample 3 putative correspondences
		2. compute up to 4 R and C using PnP method
		3. Check inliers by $d(P_3X_j)\le\sigma\sqrt {5.99}$
	4. Do bundle adjustment with Geometric Error on all views.