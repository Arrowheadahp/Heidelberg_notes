We want to find long edge chains

Edges can be shown by getting the 1st derivative of the picture after convolution so as to not detect noise.$$ \frac{d}{dx}(g*f) = (\frac{d}{dx}g)*f
$$
But Because $dx$ is 1 pixel, the derivative becomes $$ f(x+1)-f(x) $$
![[Pasted image 20260506031210.png|500]]


### Linking
Linking nearby edges to make chains 
1. Find good edges
2. Find true localization (true edge)
3. Find single response: one per edge
4. Find long edge-chains

Humans perceive edges very differently where edges depends on the semantic 

### Precision and Recall
How good the edges or object is detected is calculated by the [[Precision]] and [[Recall]].
We want both [[Precision]] and [[Recall]] to be high but generally its inversely related. So we plot it for different algorithms using the [[Precision-Recall Curve]] or the [[F-score]]. 

Canny edge detectors have as good [[F-score]] as humans.