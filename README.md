# **Finding Lane Lines on the Road** 

## 1. Pipeline description.
This pipeline consists of 6 steps:

#### Color Selection
Using HSV color space two mask are created for the yellow and white color range. 
The mask is aplied to the image to filter out unwanted colors.

#### Region Masking
A triangular region is defined comprised of bottom corners and the center of the image, where the road is located.

#### Canny Edge Detection
To improve the edge detection two transformations were applied:
- Convert images into gray scale to simplify detecting the edges on the image
- Gaussian smoothing for suppressing noise and spurious gradients

#### Hough Transform
The Hough transform is applied to obtain the line's points of the edges calculated on the previuous step.

#### Slope, intercept and length of Hough lines
The slope, intercept and length of all the lines were calculated.
The side of the road of each line is determined by the slope sign.

### Weighted mean of the lines of each side
Right and left lane lines are calculated as the weigthed mean of the lines of each side.
Lengthly lines has more importance in order to obtain the main lines.

## 2. Potential shortcomings
Potential shortcomings would be what would happen when dealing with:
 - Sharp corners
 - Lane changes
 	- Own car 
 	- Other cars
 - Night
 - Low visibility
 	- Rain
 	- Fog


## 3. Possible improvements
Possible improvements would be to:

 - Horizon line calculation
 - Polynomial curve fitting


