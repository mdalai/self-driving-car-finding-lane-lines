# **Finding Lane Lines on the Road** 

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


![Output](/test_images_output/solidWhiteRight.jpg)
---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps:
 - 1. convert images to grayscale
 - 2. Apply Canny edge detection
 - 3. Apply Gaussian blur
 - 4. Apply Region of Interest mask
 - 5. Draw hough lines
 - 6. Apply hough lines into the original image

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by:
 - find all slopes and intercepts from Hough lines; Note: if it is vertical line, exclude it.
 - if slope < 0, then it is left lane line; else it is right lane line;
 - Calculate the average slope and average intercpt of all left lane lines; do same to the right lane lines;
 - Get the two points for left lane line and two points for the right lane line; 
 - draw lines with these points in the end;

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline

 - Drawn lines on the video appearts to be not stable.
 - It has drew extra cross line in following image: ![error image](/test_images_output/whiteCarLaneSwitch.jpg
)
 - If car goes uphill or downhill, the code may not work. Because of the defined region of interest may not fit well.


### 3. Suggest possible improvements to your pipeline
 - Need better way of extrapolating lines in order to stablize the line
 - 
