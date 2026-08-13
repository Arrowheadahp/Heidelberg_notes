This uses [[Attention Mechanism]]. The Self-Attention and Cross Attention. 
1. Split the Image into N patches where N is the number of tokens in an LLM Typically 4x4.
2. Reshape and project the patches using 1x1 convolutions.
3. Add positional encoding and class encoding to get Dx2(N+1) Input
4. Run L times through transformer to get Dx2(N+1) Output
5. Take the Dx1 Class output vector. Get it into Class Distribution via an [[Neural Network]].

![[Pasted image 20260812004237.png|720]]

