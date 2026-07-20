
1. RootSIFT:
	Compare [[SIFT (Scale Invariant Feature Transform)]] vectors using a better distance than $L_2$-norm since it overemphasizes cells with large values.
	Use Hellinger-Kernel instead: $H(x,y) = \sum_i \sqrt{x_iy_i}$.
2. RootSIFT-PCA: Dimensionality reduction of SIFT vector.
3. DSP-SIFT: Histogram over various different scales