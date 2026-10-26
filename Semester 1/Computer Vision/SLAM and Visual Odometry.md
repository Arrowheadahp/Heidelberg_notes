### Some Applications for Sparse 3D Reconstruction:
#### Structure from Motion (SfM)
This is the [[Multi-view 3d Reconstruction]] in pure form. It is to create the 3D model of a place
- Creation of 3d models from (large) unordered image set
- Often Emphasis on visual quality and completeness of 3D models
- ==Offline Setting==: Speed is not very important
#### Visual Odometry (VO)
This is creating a [[Multi-view 3d Reconstruction]] of a path from images taken from a vehicle. But it does not create a map, meaning it cannot understand if the vehicle has looped back or not.
- Reconstruction from a camera path from an image stream
- Minimize accumulated error (drift) of camera path
- Maps Reconstructed, but no understanding of global topology
- Online setting: ==Real time operation==
#### Simultaneous Localization and Mapping (SLAM) 
This understands topological mapping and corrects itself for it. It combines Odometry and SfM.
- Visual Odometry and Consistent map reconstruction
- Incremental Reconstruction
- Map reliability is more important than completeness of 3D model
- ==Real Time operation==