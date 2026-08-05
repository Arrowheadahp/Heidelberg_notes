The kernel is a 2d Gaussian curve: 
$$\frac{1}{{2\pi\sigma^2}} e^{-\frac{x^2+y^2}{2\sigma^2}} $$
This is similar to [[Box Filter]] but the more nearby pixels are given more weightage than farther pixels.
This is the go to for blurring and [[Noise Removal]].