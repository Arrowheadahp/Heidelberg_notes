### Some definitions for Sparse 3D Reconstruction:

1. Structure from Motion (SfM)
   - Creation of 3d models from (large) inordered image set
   - Often Emphasis on visual quality and completeness of 3D models
   - Offline Setting: Speed is not very important
2. Visual Odometry (VO)
   - Reconstruction from a camera path from an image stream
   - Minimize accumulated error (drift) of camera path
   - Maps Reconstructed, but no understanding of global topology
   - Online setting: Real time operation
3. Simultaneous Localization and Mapping (SLAM) 
   - Visual Odometry and Consistent map reconstruction
   - Incremental Reconstruction
   - Map reliability is more important than completeness of 3D model
   - Real Time operation