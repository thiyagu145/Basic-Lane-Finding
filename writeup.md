**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

### Description of my pipeline

My pipeline consisted of 5 steps.
1) Converting the image from 3 channel to grayscale
2) Applying Gaussian Blur to the image
3) Applying canny edge detector
4) Selecting the specific region on the image using the cv2.fillPoly
5) Finding the hough lines and drawing the lines 
6) Applying it to the video 

Modification on the draw_lines() function: 
The line segments belonging to the left and right sides were extracted based on their slope values since the left side line has an increasing slope and the right side line has a decreasing slope. After the line segments were separated, the starting and ending points of the lines were decided. The starting point was from the bottom of the image since the lane lines start from the bottom and the end points were arbitrarily set and the line was drawn based on the slope values extracted from the left and right lines. numpy.polifit() was used to find the slope of the line, considering it as a first degree polynomial.


### Shortcomings
When curves are present, there are a lot of noisy lines coming up. This has to be improved. 

### 3. Improvements to the pipeline
A dynamic region of interest can be created to accomodate changes in different types of roads

