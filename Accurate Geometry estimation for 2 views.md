For example For [[Homography]] estimation, the method is:
- Repeat n times
	- select randomly 4 point corresponding $(x_1, x_2, x_3, x_4)$
	- compute homography H from the points
	- evaluate $f'(H) \sum_i f(x_i, H)$
	- if $f'(H) \le f'(H^*)$
		- $H^*\gets H$
		- $f'(H^*)\gets f'*(H)$

And in this case $$f(x_i,H)=0\ if\ ||Hx_l^i - x_r^i||_2 \le t \ else\ 1$$
This is basically [[RANSAC]] calculating the Euclidean distance between left image's homography with the right image and minimizing that. We can also the difference between right image's homography. We can also average both.

### Error Functions
Here the $||Hx_l^i - x_r^i||_2$ is the error function for Homography, There are error functions for others:

- For a line: $|x_2^i+ax_1^i-b|$
- For [[Homography]]: $||Hx_l^i - x_r^i||_2$
	- It can also be: $\frac{1}{2}d||Hx_l^i - x_r^i||_2+\frac{1}{2}||Hx_r^i - x_l^i||_2$
	- Gold Standard: $$\min\left[\frac{1}{2}d||Hx_l^i -\hat x_r^i||_2+\frac{1}{2}||Hx_r^i -\hat x_l^i||_2\right]$$
- For [[Fundamental and Essential Matrix]]: $||(x_l^i)^T F x_r^i||_2$

## Final Algorithm to compute [[Homography]]:

1. [[Interest Point Detection]]: Detect Interest points using [[Harris Detector]].
2. [[Appearance Based Matching]] using [[Kd-Tree Search]] to make it fast.
3. [[RANSAC]] robust estimation: Repeat for n samples (adaptive)
	1. Select randomly 4 point corresponding $(x_1, x_2, x_3, x_4)$ and compute homography H from the points. This uses [[SVD]].
	2. Calculate the distance d for each putative correspondence. This is the error function in [[Accurate Geometry estimation for 2 views]].
	3. Compute the number of inliers consistent with H by number of correspondences for which $d<t=\sqrt{5.99}\sigma$ pixels (95% confidence interval for 2d). This is $t=\sqrt{3.84}\sigma$ for 2d line and F matrix. It is actually the 2-tailed z score for $\alpha=0.05$.
	Choose the H with largest number of inliers.
4. Optimal Estimation: re-estimate H from all correspondences classified as inliers by minimizing the ML cost function using any [[Iterative Estimation Methods]]
5. [[Guided Matching]]: Further interest point correspondences are now determined using the estimated H to define a search region about the transferred point position.