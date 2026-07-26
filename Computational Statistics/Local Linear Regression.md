This creates a separate linear models for each point according to weightage of other points from that point. It minimises the localized weighted least squares.
$$J(\beta)=\sum_{i=1}^Nw_i(x)(y_i-\beta x) $$
where w is the weightage of each predictor.
$$w(x_i)=exp\left({-\frac{(x_i-x)^2}{2\tau^2}}\right)$$

In matrix form, 
$$\beta(x)=(X^TWX)^{-1}X^TWy $$