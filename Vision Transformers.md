This uses Attention Mechanism. The Self-Attention and Cross Attention. 
1. Split the Image into N patches where N is the number of tokens in an LLM.
2. Reshape and project the patches
3. Add positional encoding and class encoding to get Dx2(N+1) Input
4. Run L times through transformer to get Dx2(N+1) Output
5. Take the Dx1 Class output vector. Get it into Class Distribution via an [[MLP]].