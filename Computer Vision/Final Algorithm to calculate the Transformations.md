## Final Algorithm to compute [[Homography H]]:

1. [[Interest Point Detection]]: Detect Interest points using [[Harris Detector]].
2. [[Appearance Based Matching]] using [[Kd-Tree Search]] to make it fast.
3. [[RANSAC]] robust estimation: Repeat for n samples (adaptive)
	1. Select randomly 4 point corresponding $(x_1, x_2, x_3, x_4)$ and compute homography H from the points.
	2. Calculate the distance d for each putative correspondence. This is the error function in [[Accurate Geometry estimation for 2 views]].
	3. Compute the number of inliers consistent with H by number of correspondences for which $d<t=\sqrt{5.99}\sigma$ pixels (95% confidence interval for 2d). This is $t=\sqrt{3.84}\sigma$ for 2d line and F matrix. It is actually the 2-tailed z score for $\alpha=0.05$.
	Choose the H with largest number of inliers.
4. Optimal Estimation: re-estimate H from all correspondences classified as inliers by minimizing the ML cost function using any [[Iterative Estimation Methods]]
5. [[Guided Matching]]: Further interest point correspondences are now determined using the estimated H to define a search region about the transferred point position.