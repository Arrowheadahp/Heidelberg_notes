Histogram of Oriented Gradients
This method uses [[SIFT (Scale Invariant Feature Transform)]] to get a feature vector. 
- Compute Gradients on an image of 64x128 pixels
- Compute histograms on cells of typically 8x8 ixels
- Normalize Histogram within a block. A block has 2x2 cells (7x15 overlapping blocks)
- Final HOG feature Vector (3780D=7x15x4x9)

### Training: 
1. Map image to Feature space
2. Train with positive and negative ([[Support Vector Machines]])
### Testing
1. Map image into feature space (HOG)
2. Scan image with 64x128 boxing all scales and all locations and compute SVM score.
3. Perform Thresholding and non-maximimum suppression
4. Report final boxing

### HOG Limitations
- Single rigid template is oftentimes not enough to represent an object category due to different viewpoints, color, style etc.
- some object classes like humans are articulated, have parts that can vary in configuration
