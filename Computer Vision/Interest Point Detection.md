This is used to match where things are moving from one image to another.
Goal is to predict a few points that are invariant against
1. Geometric transformation: Scaling, rotation, translation, affine transformation. All are invariant in [[Projective Geometry]].
2. Colour transformation: lighting change (additive), contrast (multiplicative), both, etc
3. Discretization (ex: spatial resolution)

Points are better for this role because corners are easier to pinpoint in a image than line segment which can be anywhere on the line.

One of the algorithms used for detecting these is [[Harris Detector]]. There are other algorithms that uses regions instead of corners but corner detection works best. 
