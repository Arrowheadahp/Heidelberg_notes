Novel View Synthesis is a task which consists of generating images of a specific subject or scene from a specific point of view, when the only available information is pictures taken from different points of view.

Where [[3D Reconstruction]] pipeline also known as Photogrammetry approach does the following things in order:
1. Input Images
2. Camera poses and sparse point cloud
3. Compute dense depth maps for each image pair
4. Dense 3D reconstruction
5. Meshing
6. Texture mapping
7. Rendering of new views (Rasterization, Ray tracing)

Image based rendering allows the use of multiple 2 dimensional images in order to generate directly 2 dimensional images.

This can be done by 2 methods:
- [[NERF]]
   - Needs Camera poses only
   - Slow (test, train) but high quality
   - Can handle view-dependent effects ex: reflections
- [[3D Gaussian Splatting]]
   - Needs Camera poses AND sparse point cloud
   - Fast (train and test) and high quality
   - Cannot handle view dependent effects in first version.

