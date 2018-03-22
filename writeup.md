# **Finding Lane Lines on the Road** 

## Writeup File

### Here is the file discripe the pipeline and some suggestion for the project

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe the pipeline. 

My pipeline consisted of 4 steps. First, I converted the images to grayscale, then I use the gaussian blue to decrease the noisy in the image. After that, use canny algorithm to get the edges and wipe off the distraction edges around the lane by set regiono of interest(ROI). Last but not least, use cv2.HoughLinesP operator to get the target lanes correctly and draw lines on the origional image to display the result.

### 2. Modify the draw_lines() function
In order to draw a single line on the left and right lanes, I modified the draw_lines() function by increase the line thickness up to 10, which seems include the hole lane mark. In order to make the result more precisely, I choose to use line slope((y2-y1)/(x2-x1)) to exclude the distraction out of the angle range.

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be have poor performence when meet the curve lane.

Another shortcoming is the result could be distracted by shadows, cars or damaged lanes


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use perspective projection to tranform image to bird's eye view, and then detect vertical line with angle range limited.

