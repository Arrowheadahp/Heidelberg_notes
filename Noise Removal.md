[[Image Filtering]] can be done to remove noise

There are multiple [[Sources of Noise]].

Assumption: Neighbouring pixels contain the information about the intensity of the centre pixel.

- If the noise added follows [[Gaussian Distribution]], it can be derived that the best filter to get the true value is a [[Box Filter]]
- For outlier noise removal [[Median Filter]] can be used.
- For noise removal from different picture, [[Bilateral Filter]] can be used.
