This is a type of [[Auto-Encoders]] which is used for [[Image Generation]]. 
Here along with the Reconstruction loss, a Unsupervised distribution loss is also added.

![[Pasted image 20260812232159.png|720]]

The bottleneck is 2 parts that encodes mean and a standard deviation of a probability distribution and the KL is enforcing that it is a  [[Gaussian Distribution]].