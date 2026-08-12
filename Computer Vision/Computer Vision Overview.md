#overview 
### [[Introduction to Computer Vision]]
The main objective is to get information from pictures. This information can be physical like getting geometry or camera properties or motion, or semantic like recognising objects in the picture
### [[Basics of Image Processing]]
To get the information we need from pictures, we use [[Image Filtering]] of which there are 2 types. 
1. [[Image Convolution]] is the linear variant which is so widely used is because of the [[Properties of Convolution]] and also [[Convolutional Neural Networks]] can learn the weights of the convolution filter during training.. There is a [[List of Convolution Filters]] that are used for various other things and even though Matrix multiplication is the best way to perform [[Computation of Convolutions]], some filters are separable and therefore computation can be done faster.
2. There are some Non-Linear Variants as well like [[Median Filter]] which does a better job of denoising and [[Bilateral Filter]] that can sense edges in the image as well.

These processing can be used in multiple applications like 
1. [[Multi-Scale Image Representation]] that uses [[Gaussian Filter]] for blurring before changing the scale to stop aliasing and other artifacts.
2. [[Edge Detection and Linking]] that uses [[Sobel Filter]] for [[Edge Detection]] and then [[Linking for Edge Chains]] using [[Hysteresis]].
3. [[Interest Point Detection]] that uses [[Edge Detection]] and [[Harris Detector]] to get some points in the image that are easily identifiable.
### [[3D Reconstruction]]
#### Purpose
Here the objective is to perform [[Multi-view 3d Reconstruction]] which is to create a 3d model from images taken from different angles and locations. This is done by starting with 2 images and calculating the transformation that happened between them called the [[Fundamental Matrix F]]. Then successively add more images to it while using [[RANSAC]] on the Geometric points in Real 3d. This Reconstruction is used in applications like creating a 3d map of a place or [[SLAM and Visual Odometry]].
#### Transformations
For that we have to get the exact transformation that happens from 1 image to another. These transformations are 

| Symbol | Transformation           | Description                                  | DoF | Min points                 | Formula                                         |
| ------ | ------------------------ | -------------------------------------------- | --- | -------------------------- | ----------------------------------------------- |
| H      | [[Homography H]]         | Transformation matrix for Rotated Camera     | 8   | 4                          | $x_1=Hx_0$<br>$H=K_1RK_0^{-1}$                  |
| F      | [[Fundamental Matrix F]] | Transformation between 2 un-calibrated views | 7   | 8 (7 for 1 or 3 solutions) | $x_0^TFx_1=0$<br>$F=K_0^{-T}T_\times RK_1^{-1}$ |
| E      | [[Essential Matrix E]]   | Transformation between 2 calibrated Views    | 5   | 5                          | $x_0^TEx_1=0$<br>$E=T_\times R$                 |
To calculate these transformations, we need the transformation that happens when a 3d world is transformed into a 2d image by a [[Camera]]. This transformation is the [[Camera Matrix P]] which is calculated by [[Camera Calibration]]. It consists of the projection [[Camera Calibration Matrix K]], Rotation R, Translation C. $$x=KR(I-\tilde C)X=PX $$

| Symbol | Transformation                  | Description                                                                                              | Degrees of Freedom |
| ------ | ------------------------------- | -------------------------------------------------------------------------------------------------------- | ------------------ |
| P      | [[Camera Matrix P]]             | Complete transformation from 3d to image                                                                 | 11                 |
| K      | [[Camera Calibration Matrix K]] | This is the Camera intrinsic transformation which <br>includes the focal length, magnification and skew. | 5                  |
| R      | Rotation                        | Orientation of the camera                                                                                | 3                  |
| C      | Translation                     | Location of the Camera                                                                                   | 3                  |
#### [[Final Algorithm to calculate the Transformations]]
How we calculate the Transformations is that let's say we have 2 images, we perform [[Interest Point Detection]] on both images. This is done by detecting corners using the [[Harris Detector]]. Then we perform [[Appearance Based Matching]] using [[SIFT]] or similar methods like [[LIFT]] . This encodes patches of the image so that a matching patch can be found in other images. We find the matching pairs of points by using a [[Kd-Tree Search]]. Then we perform [[RANSAC]] on the matching points to remove the outliers and the noise from the inliers and get the transformation we need. Most of the time it is F or E.
### [[New View Synthesis]]
We can use pictures taken in a view and generate views from different perspectives. This is done by methods: 
1. [[NERF]] which is a slow method that uses [[Neural Network]] on images in only [[Fourier Cosine Basis]] but can handle view dependent effects like reflections.
2. [[3D Gaussian Splatting]] which is a faster process that uses [[3D Reconstruction]] but cannot handle view dependent effects.
3. Photogrammetry: This uses a triangle mesh to create a 3d model that is then rendered using [[Graphics]].

### [[Graphics]]
The rendering is created using the rendering equation: $$L_o(p, w_0)=L_e(p, w_0)+\int_Hf_r(p, w_i\to w_o)L(p,w_i)\cos\theta \ dw_i $$
Here f is the [[Scattering function]] which is dictated by [[BRDF]] which has 2 parts: [[Diffusion]] and [[Specular Reflection]].
Artists that creates the rendering are mostly interested in 3 things of a surface:
1. Colour: also called albedo. This is how an object looks like when there is ambient light from all sides.
2. Metallicity: The colour of [[Specular Reflection]] is dictated by the colour of the metal. No [[Diffusion]]
3. Roughness: This dictates the [[Specular Reflection]] as well according to the Cook Torrance [[BRDF]]
There are other things like Subsurface scattering and Fresnel effect that are important.
### [[Object Recognition]]
This is a wide field which can be subdivided into 3  successive parts:
1. What is there? 
   [[Object Detection]]: Creates bounding boxes 
	   This is done by old techniques like [[HOG]] and [[DPM]] and NN methods like [[R-CNN]] and new techniques like YOLO.
2. Where is it?
   [[Semantic Segmentation]]
3. If there are more, which is which?
   [[Instance Segmentation]]
### [[Image Generation]]
### [[Training Data Generation]]