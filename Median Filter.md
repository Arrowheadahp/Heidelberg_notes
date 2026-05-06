This is another good method for [[Noise Removal]] and it works better than [[Box Filter]]. 

It is very good to remove outliers that come with shot noise.

Here the true value $y_r^*$ is 
$$
y^* = argmax_y (p(y|x))
$$
where 
$$ p(y|x) = p(x|y) \sim \prod_{r}\prod_{r^`\in W(r)}{e^{-\frac{|x_{r^`}-y_r|}{2\sigma^2}}} 
$$
So$$ 
log(y^*) = -\frac{1}{2\sigma^2}\sum_{r^`\in W(r)}{|x_{r^`}-y_r|}
$$
It is not Differentiable but it is convex.

$$ y^*_r = Median_{r}(x_r) $$