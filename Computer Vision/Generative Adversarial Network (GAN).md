![[Pasted image 20260812125635.png|720]]

### Training Objective
$$\min_G\max_DL(D,G)=\mathbb E[\log D(x_{real})] + \mathbb E[\log(1-D(G(z)))] $$
The Generator tries to maximize the loss that the discriminator is getting while the discriminator is trying to minimize the same loss of classifying if an image is real or not.

It is trained in iterative fashion since it is generally hard to train a min-max algorithm which often does not converge. Sometimes Generator does not change even when discriminator does or vice versa due to Nash Equilibrium

#### Conditional GAN
Real images are given with additional conditional images
#### Cycle GAN
This is image to image translation