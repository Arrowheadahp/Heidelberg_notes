https://youtu.be/Z_HwkG90Yvw?si=0HpuL0pW1hRSj2Kf

$$ R = \lambda_1 \lambda_2 + k(\lambda_1+\lambda_2)^2
$$
R is the H-Score
k takes the value of 0.04
$\lambda$ are the lengths of the ellipse that is created after plotting the derivatives in x and y directions such as in [[Edge Detection and Linking]]. To check if both $\lambda$s are big, Harris made the above equation that can be checked with a threshold.

### Non-Maximal Suppression

All the pixels near the corner gets high H-Score so Non-Maximal Suppression. Here the scores of all the pixels within a radius r is checked for each pixel p with H-score > threshold . if p has the maximum value in that radius then it is the corner. 
the radius r controls the number of corners to keep.