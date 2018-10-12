# **Finding Lane Lines on the Road** 

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. 

First, I converted the images to grayscale with cv2.cvtColor method.
Then I applied a Gaussian blur to the gray image with cv2.GaussianBlur method
After that, I use cv2.Canny method to find edges on the image.
Then, I eliminate parts of the image because I was only interest in the specific region
Then, use a Hough transfromation to find out the lines on the interest region with HoughLinesP method
Finally, merged the output of Hough transformation and origninal image and we can find lines on original image.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function.
I seperate the lines into right lines and left lines, 
and then use the average of right/left lines slope as the slope of right/left line.
Then find out the start point and stop point by find the minimum and maximum y.
Use the method cv2.line, I could draw the lines.




### 2. Identify potential shortcomings and improvements with your current pipeline


One potential shortcoming would be that in the second video, there are some shakes on the image.
I suppose it was because the speed of ego vehicle is too high and the update frequency of image is too high,
which makes the slope of lines between two images different obviousely. That is to say, the algorithm of draw line should be improved.

Another shortcoming is I didn't finish the change video, I suppose I would finish it if I have some idea about it.

