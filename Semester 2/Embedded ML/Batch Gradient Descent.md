This is where multiple gradients from different samples are added to create a batch that is used for increments. 
So, for each sample i, $$\nabla \mathcal L=\frac{\partial\mathcal L_i}{\partial \theta}$$
So for each batch, $$\Delta \theta = \theta+\gamma\sum_i\nabla\mathcal L$$