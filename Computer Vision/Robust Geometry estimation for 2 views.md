This is to find geometrically the good matching points from all the matching points that we have. We plot $(x_1-x_0), (y_1-y_0)$. The outliers are ignored and the calculations are done only using inliers. To find the inliers, we define a straight line and for points nearby the value becomes 0 and points far, it becomes 1 and we minimise that function. $$ f= |ax_0 + bx_2 -1| \le t \to 0\ else\ 1$$
This is equivalent to getting the F such that $$f = |x_l^tFx_r|\le t \to0\ else\ 1$$
$$F* = \arg\min_F \sum_i f $$

### Naive approach
Enumerate all points and make lines with $(r, \theta)$. Hough transform and get the values for max. Very time consuming.

### Oracle
Oracle is a function that predicts a parameter given the minimum amount of data points (d-tuples): $$g(x_1, x_2)=f^{-1}(x_1, x_2)$$ For [[Fundamental and Essential Matrix]] calculation we only need 7 or 8 points. For [[Homography]] only 4 points are needed. So we make these sizes tuples. And instead of getting all the possible tuples, we sample randomly to get [[RANSAC]].
