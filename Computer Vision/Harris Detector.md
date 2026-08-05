This is an algorithm to perform [[Interest Point Detection]].
https://youtu.be/Z_HwkG90Yvw?si=0HpuL0pW1hRSj2Kf
### Algorithm:
1. First we find the derivatives of the image using [[Sobel Filter]] in both x and y directions.
2. We then plot the gradients in $I_x$ vs $I_y$
3. We fit an ellipse on the distribution. see image. This is done by getting the max moment of inertia and min moment of inertia. These are $\lambda_1$ and $\lambda_2$.
4. We calculate the Harris Corner Response function:$$ R = \lambda_1 \lambda_2 - k(\lambda_1+\lambda_2)^2
$$R is the H-Score
k takes the value of 0.04
5. We only take the values more than a threshold
6. We do [[Non-Maximum Suppression]] to only get points.
$\lambda$ are the lengths of the ellipse that is created after plotting the derivatives in x and y directions such as in [[Edge Detection and Linking]]. To check if both $\lambda$s are big, Harris made the above equation that can be checked with a threshold.
![[Pasted image 20260804191440.png]]
### [[Non-Maximum Suppression]]
All the pixels near the corner gets high H-Score so Non-Maximal Suppression. Here the scores of all the pixels within a radius r is checked for each pixel p with H-score > threshold . if p has the maximum value in that radius then it is the corner. The radius r controls the number of corners to keep.