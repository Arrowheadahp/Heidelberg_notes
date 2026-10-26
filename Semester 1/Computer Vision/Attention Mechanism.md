https://youtu.be/eMlx5fFNoYc?si=twFMpJPoGo3BQaiM

Every context window is divided into tokens (Embeddings) E
Every token is multiplied with a Query Weight W_Q to get Q
Every token is also multiplied with Key Weight W_K to get K
Q and K is dot product to get the attention value which is given to [[SoftMax Function]] for Q
Each vector of the [[SoftMax Function]] is transformed by a Value weight matrix and then output matrix that gives the $\Delta E$ which is added to the Embeddings E.

![[Pasted image 20260812002737.png]]