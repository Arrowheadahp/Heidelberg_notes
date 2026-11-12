This is a non-linear filter that makes the non maximum value into 0 while still preserving the maximum value as it is.
### Application
1. This is used in [[Linking for Edge Chains]] for finding the edge points.
2. [[Harris Detector]]: 
   All the pixels near the corner gets high H-Score so Non-Maximal Suppression. Here the scores of all the pixels within a radius r is checked for each pixel p with H-score > threshold . if p has the maximum value in that radius then it is the corner. The radius r controls the number of corners to keep.