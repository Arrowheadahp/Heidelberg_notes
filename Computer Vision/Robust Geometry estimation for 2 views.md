This is to find geometrically the good matching points from all the matching points that we have. We plot $(x_1-x_0), (y_1-y_0)$. 
![[Pasted image 20260810141535.png|512]]
There are 2 sources of error:
1. Noise because of which the line above is thick. It is because of imperfect measurements.
2. Outliers when the matching points in the images are not actually matching in real.
### Formulation
The outliers are ignored and the calculations are done only using inliers. To find the inliers, we define a straight line and for points nearby the value becomes 0 and farther points becomes 1 and we minimize that function. $$ f= |ax_0 + bx_2 -1| \le t \to 0\ else\ 1$$
This is equivalent to getting the F such that $$f = |x_l^tFx_r|\le t \to0\ else\ 1$$
$$F* = \arg\min_F \sum_i f $$

### Computation
1. Naive approach: [[Hough transform]]: Enumerate all points and make lines with $(r, \theta)$.
2. [[RANSAC]]: Instead of using all points, we randomly sample the minimum number of points required for calculating what we want to calculate and then calculate it and do that again and again. ==The method that calculates the value with the minimum number of required points is called the Oracle==. This minimum number of points depends on what we want to calculate: F needs 7 points, H needs 4 etc.


