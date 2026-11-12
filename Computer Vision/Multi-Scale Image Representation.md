This is to represent images at many scales or resolutions.
We cannot just take every 3rd pixel when down sampling. We do an [[Image Convolution]] to smooth the and then down sample. This fixes the issue with aliasing effects.
![[Pasted image 20260804141241.png]]

[[U-Net]] can also be used for this purpose.

### Applications
1. Also can be used for template search.![[Pasted image 20260506030040.png]]
2. Segmenting large images