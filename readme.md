# **Finding Lane Lines on the Road** 


### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps:

+ convert the images to grayscale
+ use gaussian blur to remove some noise
+ find edges
+ mask region of interest
+ apply hough transforms to find lane lines

In order to draw a single line on the left and right lanes, I modified the hough_lines() function by 

+ filter the unreasonable gradient whose absolute value is larger than 0.8 or less than 0.5
+ calculate lane line making the height between 320 and 550
+ averge the left and right lines above 



### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when some noise occurs in the interest region 


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use momentum（An optimization method used in neutral network）to make the result more stable.

### 4. Reviews from udacity

Good work describing your current pipeline and figuring out some potential shortcomings and possible improvements.

Whereas more possible improvements are:

+ Image from infrared camera.
+ Adding an outlier reduction approach like RANSAC on the hough lines.
+ Using curve fitting to plot the curve instead of straight lines.

Furthermore, the following changes that might help you in certain conditions like curved lanes, shadows etc.

+ Increasing min_line_len and max_line_gap for Hough Transform close to 100 will make your lines longer.
+ You took kernel-size of the Gaussian filter as 5, decreasing this will remove the noise making the image less blurry.

Congratulations for passing this project!

Good luck with future submissions :)


