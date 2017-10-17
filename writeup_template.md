# **Finding Lane Lines on the Road** 
---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied a gaussian blur function to reduce noise, then I used a Canny function to find the lines, then I masked out the region that contained the lane lines, then I applied a Hough function to draw the lines and finally superimposed the lines over the original video or still.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by to first separate left lane from right lane, then I eliminated the lines with the outlying slope, then I averaged the lines and crated a linea equasion describing the average lines, then finally I extended the lines to the y origin and an appropriate height on the screen.


### 2. Identify potential shortcomings with your current pipeline

The shortcomings are as follows:

1. The angle of the camera to the road changes the mask and some lines are missed as a result.
2. Shadows create problems in line detection.
3. Some frames are missing lines.

### 3. Suggest possible improvements to your pipeline

1. Add an averaging function to average lines between frames.
2. Look for when the lines cross and resuce the height accordingly.
3. Increase contrast to deal with shadows.
