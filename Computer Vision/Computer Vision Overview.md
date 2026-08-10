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
Here the objective is to create a 3d model from images taken from different angles and locations. For that we have to get the exact transformation that happens from 1 image to another. These transformations are 

| Symbol | Transformation           | Description                                  | Degrees of Freedom | Min points |
| ------ | ------------------------ | -------------------------------------------- | ------------------ | ---------- |
| H      | [[Homography]]           | Transformation matrix for Rotated Camera     | 8                  | 4          |
| F      | [[Fundamental Matrix F]] | Transformation between 2 un-calibrated views |                    |            |
| E      | [[Essential Matrix E]]   | Transformation between 2 calibrated Views    |                    |            |
To calculate these transformations, we need the transformation that happens when a 3d world is transformed into a 2d image by a [[Camera]]. This transformation is the [[Camera Matrix P]] which is calculated by [[Camera Calibration]]. It consists of the projection [[Camera Calibration Matrix K]], Rotation R, Translation C. $$x=KR(I-\tilde C)X=PX $$

| Symbol | Transformation                  | Description                                                                                              | Degrees of Freedom |
| ------ | ------------------------------- | -------------------------------------------------------------------------------------------------------- | ------------------ |
| P      | [[Camera Matrix P]]             | Complete transformation from 3d to image                                                                 | 11                 |
| K      | [[Camera Calibration Matrix K]] | This is the Camera intrinsic transformation which <br>includes the focal length, magnification and skew. | 5                  |
| R      | Rotation                        | Orientation of the camera                                                                                | 3                  |
| C      | Translation                     | Location of the Camera                                                                                   | 3                  |
