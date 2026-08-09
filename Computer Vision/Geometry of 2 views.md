### Part 1: When the camera is only rotated and not moved
[[Homography]]
### Part 2: When the camera is rotated and moved
When the [[Camera Calibration Matrix K]] is not known for any of the 2 views, the transformation is called the [[Fundamental Matrix F]].
When the K values are known, the remaining transformation is called the [[Essential Matrix E]].

[[Fundamental and Essential Matrix]]: With more than 7 matching points, we can make a matrix that can encapsulates the transformation that happens when the camera is moved from 1 place to another.

The basic idea is that in 3d [[Projective Geometry]], each matching point pair makes a plane with the camera centres.