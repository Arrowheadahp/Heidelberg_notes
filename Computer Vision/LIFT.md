## Learned Invariant Feature Transform
### Pipeline
![[Pasted image 20260809131857.png|720]]
1. DET: Detector that creates the 2d feature map
2. NMS: [[Non-Maximum Suppression]] This is to get the feature size having the maximum "featured-ness"
   This is substituted by soft argmax ([[SoftMax Function]]) to keep it differentiable.
3. Crop: to get the patches with the scale of the features
4. ORI: Orientation angle determined
5. Rot: Rotation to get the orientation correct
6. DESC: Descriptor extraction (convert each patch into vectors for comparison)
### [[LIFT]] vs [[SIFT]]
- for easy cases, LIFT finds more matches than SIFT but
- For harder cases, SIFT finds more matches than LIFT
- LIFT is much slower than SIFT

Therefore SIFT is overall better
