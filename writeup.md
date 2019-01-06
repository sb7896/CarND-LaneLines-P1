# **Finding Lane Lines on the Road** 

[//]: # (Image References)

[image1]: ./test_images/output.png "Solid White"

### 1. Pipeline

My pipeline consists of 5 steps:

1. Convert the images to grayscale
2. Apply Gaussian blur to the images
3. Find edges using Canny edge detection algorithm
4. Select region of interest.
5. Find lines using Hough transform

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by:
1. Identify lines based on whether slope is positive or negative. Left lane has positive slope, while right lane has negative slope.
2. Calculating the average for left and right slopes.

![Image after applying pipeline][image1]

### 2. Potential Shortcomings

One potential shortcoming would be what would happen when there is a turn. For example, if there is a left turn, code will not predict lanes correctly.

Another shortcoming is there are some parameters that might only work well with the given test images, they may not work correctly for other images


### 3. Possible Improvements

First possible improvement would be to figure out how to handle left/right turns. Second possible improvement is to handle a wide range of images. For example, images in different lighting conditions.
Third possible improvement would be to use HSV/HSL instead of RGB to correctly identify colors.
