Find oriented patches around interest points to capture appearance
   Problems with capturing appearance
	1. Deal with ==orientation==: `np.arctan2(Iy, Ix)`		   ![[2D Gradient]]
	2. Deal with ==scale== (zoom)
	    Choose a patch of pixels around each interest point. We can do [[Edge Detection]] using alternate method of [[Laplacian of Gaussian (LoG)]] operator. We then plot the $f$ (LoG value) wrt to different $\sigma$. $f$ is the average "edge-ness" in all directions. We then match these curves to find unique corresponding points.
Result is a list of patches with that are rotated along the orientation.