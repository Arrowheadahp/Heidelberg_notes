It keeps the sharp edges but is computationally inefficient. #todo

This looks at 
1. Distance to surrounding pixels (like gaussian)
2. Intensity of surrounding pixels

Computation is O(Nw). Approximation can be done in O(N).

>Joint bilateral Filter can be used to get the edges from one image and use it to [[Image Filtering]] another image

It can also be used in HDR compression, cartoonization, edge detection