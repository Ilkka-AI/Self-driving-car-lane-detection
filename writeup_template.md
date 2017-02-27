
**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I used Canny edge detection to detect all lines in the image. I then applied a region of interest mask to choose a field of view from the image that represents the immediate path in front of the car where the lanes are located. This left only the edges that represent the actual lanes. I then converted the found lanes into a single solid left line and a right line. 

In order to draw a single line on the left and right lanes, I construced a new function interpolation(). I choose the lanes that represent left lanes (same for the right lanes) using criteria for the slope and intercept values. These values were determined by observing the data. I then calculate the average slope and intercept of those lines to represent the average lines. The position of the left and right lanes can then be calculated in the image by setting the lanes to start in the bottom of the image and end around the middle. 

I did not use the color detection as I don't think it was really needed and lanes can be of different colors. I also did not use noise averaging as I understood this was done anyway in the Canny function. 


###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the image is of different resolution. This would be an easy fix. 

Other shortcomings could be that the pipeline does not work so well in bad weather, dark, if the lane markings are worn out and therefore short or if there are other cars closeby in the front. 


###3. Suggest possible improvements to your pipeline

With more time an adaptive field of view could be constructed. Also averaging over subsequent images (videoframes) could improve the detection. Parameters could of course be tuned much more carefully. 


