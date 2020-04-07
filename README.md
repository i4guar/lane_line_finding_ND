This is the first project as part of the Self Driving Cars Nanodegree by Udacity.

[Link to my jupyter notebook containing my code](./P1.ipynb)


# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. 
First, I converted the images to grayscale, then I applied a gaussian blur to reduce the noise of the image and improve the next step (edge detection). 
The edge dectection was done with the canny algorithm. 
Thereafter I use the region of interest to filter out all edges of the environment. 
Lastly I determined the hough lines.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by calculating the average offset and slope of the left and right lane line, respectively. 
The hough lines of the right and left lane can be distinguished by the leading sign of the slope (wether it is positive or negative).


### 2. Identify potential shortcomings with your current pipeline


If a hough line is detected falsely it has a heavy impact on the resulting lane line, as I don't remove outliers before averaging the lines.

Additionally, my pipeline can only detect straight lane lines, which is not how the lane lines are in real life.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to consider color in my algorith, although the time of day and weather condition should be taken into consideration when using color and be color corrected.

Another potential improvement could be to invest more time to optimize the parameters for the various filters (canny, hough and gaussian) I am using.
