# **Finding Lane Lines on the Road** 

## Project Report

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:

* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. My pipeline description.

My pipeline consisted of x steps.

1. I select image color that is bright, because Lane line color is relartivly brighter.
2. I converted the images to grayscale.
3. I apply gaussian blur on iamge
4. then I do canny feature extraction.
5. and apply some ploygon mask on the image to mute some noise
6. finally, I do hough_line to extract line feature. In this fuction, It turns out many lines, but I modified the draw_lines() function by select lines that would intersect with the bottom line. And I skip the frame if there is not lan line detected to prevent programme collapse 



### 2. Identify potential shortcomings with your current pipeline


potential shortcoming would be as follows:

1. some dotted lane line would not be detected when then are very far apart
2. when the road is very bright the lane line is not so easy to be detected


### 3. Suggest possible improvements to your pipeline

Possible improvement would be as follows:

1. make the program detecte exactly two lane lines, that is one left and one right
