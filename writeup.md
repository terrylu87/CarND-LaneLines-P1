# **Finding Lane Lines on the Road** 


---

**Finding Lane Lines on the Road**


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I blur the image by 5*5 kernel, then use cany edge detection to detect the lane, then create a ROI, then use hough transform to detect lane in the ROI.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by using polyfit fuction provided by numpy.


### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when the output of hough function provided too many stright line that is actually not a lane. The polyfit will not fit a right lane in such cases.

Another shortcoming could be the edge detection under the complicated light condition. Just like the optional video, there will be some horizontal line detected by cany algorithm which is not actually a lane.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to adjust hough funciton more carefully, so that the false detection rate could be reduced.

Another potential improvement could be to take the detection result of previous frame as a reference.
