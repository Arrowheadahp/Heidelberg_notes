Splitting the domain space recursively using decisions to make uniform-ish spaces. 
![[Pasted image 20260428190643.png]]


It is done by maximizing Information gain.$$
I(S, \theta) = H(S) - \sum_{i\in L,R} \frac{|S_i|}{|S|}H(S_i)
$$
Here $|S|$ is the number of objects. i is for each division by the tree.

Entropy equation: Shannon's Entropy
$$
H(S) = -\sum_{c\in C} p(c)log(p(c))
$$
Here p(c) means fraction of class c in the split

> [!NOTE] Loss Function
> Think of the Shannon's Entropy as the [[Loss Function]] and minimizing it will give the decision boundaries

[[Overfitting]] can be avoided in this case by 
1. placing the decision boundaries midway between bordering objects ([[SVM]])
2. Not making the tree too deep
[[Generalization]]: Overfit model does not generalize well.
 