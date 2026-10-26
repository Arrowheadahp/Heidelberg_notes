For example For [[Homography H]] estimation, the method is:
- Repeat n times
	- select randomly 4 point corresponding $(x_1, x_2, x_3, x_4)$
	- compute homography H from the points
	- evaluate $f'(H) \sum_i f(x_i, H)$
	- if $f'(H) \le f'(H^*)$
		- $H^*\gets H$
		- $f'(H^*)\gets f'*(H)$

And in this case $$f(x_i,H)=0\ if\ ||Hx_l^i - x_r^i||_2 \le t \ else\ 1$$
This is basically [[RANSAC]] calculating the Euclidean distance between left image's homography with the right image and minimizing that. 

### Error Functions
Here the $||Hx_l^i - x_r^i||_2$ is the error function for Homography, There are error functions for others:

- For a line: $|x_2^i+ax_1^i-b|$
- For [[Homography H]]:
	- This is the L2 error: $||Hx_l^i - x_r^i||_2$
	- We can also use the geometric error:
	  This is the distance between the x and the x calculated from x'. Then we add the same for calculating x' and average them $$\frac{1}{2}d||Hx_l^i - x_r^i||_2+\frac{1}{2}||Hx_r^i - x_l^i||_2$$
- For [[Fundamental Matrix F]]: $||(x_l^i)^T F x_r^i||_2$

