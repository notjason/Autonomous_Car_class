# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

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

My pipeline consisted of 
First, turing the image into a grayscale image. This made it much easier to work with.
Once the image was grayscale, I used a guassian blur to soften the edges a bit. 
Softening the edges a bit made it easier to use a canny detection to find the edges. 
Because there are a lot of edges in the image, I setup a region of interest to limit the edges to where I cared about.
Using canny edges in the region of interest, I used a hough transform and drew lines where the linese of the road was.
Then planced the lines on the image.

To make it easier, I chose to print out each image aftere each part of the pipline, so I could more easily identify where the issues  were when  I was adjusting the parameters.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when  the road curves. the apex and lines are fairly set in stone so any curves or wide lanes would be difficult to deal with. In addition, roads with potholes, or missing lines would lose track of the line. It also doesnt identify lanes on either side.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use a model to predict where the lines are likley to go by tracking where they have been. For example if a road is curving, there will be a general turn to it, and if we can predict, track those turns we can more easily change the region of interest.The same would be for lane lines that disappear, if we can use a model to detect where they should be, we can extend the lines for a period of time.

