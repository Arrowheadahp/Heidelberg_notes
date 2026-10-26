> [!Question] How to match 2 objects are the same when taking images from 2 different angles and different zoom.
## Pipeline: 

### 1. Find Interest points 
using [[Interest Point Detection]].
### 2. Define Appearance using [[SIFT]]
![[Define Appearance using SIFT]]
### 3. Encode Appearance
 Encode Patch Appearance using a descriptor
   Different methods to encode patch appearances so that it can be recognized again in a different photo taken with different angles, colour, scale etc.
	1. [[SIFT]] 
	2. [[Improvements to SIFT]]
	3. [[LIFT]]
### 4. Match Appearance 
Find matching patches according to appearance
- Goal is to find the each patch from one image to another.
- Accept all the matches that are close enough
- Methods:
	- Naïve: $N^2$ tests: Checking how close one appearance is to another is by getting the squared difference.
	- Hashing
	- [[Kd-Tree Search]] which is $n\log n$ tests.
### 5. Verify Appearances 
Verify patches according to Geometry by [[Robust Geometry estimation for 2 views]].