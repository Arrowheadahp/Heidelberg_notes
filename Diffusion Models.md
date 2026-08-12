These models are used for [[Image Generation]] by iteratively removing noise from complete noise to get the object given in a prompt and remove objects in the negative prompt.

The model trains on removing added noise from images with something like [[U-Net]].

![[Pasted image 20260812140822.png]]

### Improvement: Stable Diffusion
Moving to latent space (Encoded space)

![[Pasted image 20260812141501.png|720]]

### Improvement: Diffusion Transformer
This uses [[Transformer]] instead of [[U-Net]]