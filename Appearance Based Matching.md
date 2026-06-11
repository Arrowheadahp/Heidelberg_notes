
> [!Question]
> How to match 2 objects are the same when taking images from 2 different angles and different zoom.

## Pipeline: 

### 1. Find Interest points 
using [[Interest Point Detection]].
### 2. Define Appearance
Find oriented patches around interest points to capture appearance
   Problems with capturing appearance
	1. Deal with orientation: 
		   `np.arctan2(Iy, Ix)`
	2. Deal with scale (zoom)
	3. Choose a patch of pixels around each interest point. We can do [[Edge Detection and Linking]] using alternate method of [[Laplacian of Gaussian (LoG)]] operator. We then plot the f (LoG operator) wrt to different $\sigma$ (noise in the [[Gaussian Distribution]]). f is the average "edgeness" in all directions. We then match these curves to find unique corresponding points.
Result is a list of patches with that are rotated along the orientation.
### 3. Encode Appearance
 Encode Patch Appearance using a descriptor
   Different methods to encode patch appearances so that it can be recognized again in a different photo taken with different angles, colour, scale etc.
	1. [[SIFT (Scale Invariant Feature Transform)]] 
	2. [[Improvements to SIFT]]
	3. [[LIFT]]
### 4. Match Appearance 
Find matching patches according to appearance
	- Goal is to find the each patch from one image to another.
	- Accept all the matches that are close enough
	- Methods:
		- Naive: $N^2$ tests: Checking how close one appearance is to another is by getting the squared difference.
		- Hashing
		- [[Kd-Tree Search]] which is $n\log n$ tests.
### 5. Verify Appearances 
Verify patches according to Geometry