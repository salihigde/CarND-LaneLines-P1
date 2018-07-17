# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/grayscale.jpg "Grayscale"
[image2]: ./test_images_output/gaussianBlur.jpg "Gaussian Blur"
[image3]: ./test_images_output/canny.jpg "Canny"
[image4]: ./test_images_output/regionOfInterest.jpg "Region Of Interest"
[image5]: ./test_images_output/houghLines.jpg "Hough Lines"
[image6]: ./test_images_output/weightedImg.jpg "Weighted Image"

---

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I used the gray scale image and applied gaussian blur to that image, then I used Canny Edge Detection to determine the edges of the image according to my low and high threshold values. Then I used region_of_interest helper function to get a region of the image that I would like to proceed with, then I used Hough Transform to draw the lines to left and right lanes and finally I called weighted_img helper function to add my image with edges with the orginal image.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by determining left and right lines depending on the negative and positive slope. After the left and right lines are found I calculated average slope and intercept values for each left and right lanes. Then I used average intercept values to determine min and max points for drawing a one big lane by using our average slope value. To show a thick line I increased the thickness of the line to 15.

![alt text][image1]
![alt text][image2]
![alt text][image3]
![alt text][image4]
![alt text][image5]
![alt text][image6]


### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when in some parts of the yellow line video where in groud there is some parts which are detected as a line even though it isn't 

Another shortcoming could be in my current code the video for challenge.mp4 has issues to determine the lines properly.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to finding a way to fine tune the input parameters for canny edge detection and hough transform algorithms. In my case it took quite a lot time for finding the correct parameters

Another potential improvement could be to finding a way for fine tuning the region picking call to determine a proper area for processing.
