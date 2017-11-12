# **Finding Lane Lines on the Road**
[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

## The goals / steps of this project are the following:

The goal of the project is to find the lane lines in front of
us on a video file and paint them.

### Pipeline

My pipeline consisted of 5 steps.

1 - First, I converted the images to grayscale, 

2 - then I apply gaussian blur to this grayed image

3 - As the third i find the edges by applying Canny edge detection algorithm

4 - Then i mask the image where only the region of interest i have selected left

5 - Then i apply Hough transform and draw the extrapolated lines using my own draw_lines() function

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by first finding the line slopes and then divide those lines to two, where minus slope lines will be on the left lane and plus slope ones will be on the right.

Then i found an average point in the middle somewhere using all those lines starting and end points. Then using extrapolating ("average left slope" value and bottom and top intersection points (bottom is chosen as y_max = 539, top is chosen as y_min = vertice value + 20) Vertice value is taken from the area of interest)

I have applied several versions of this method to sample pictures. Now i have concentrated on videos and focused on fine tuning parameters according to videos. So, no picture is included in this report.

2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when there's minimum and very short lines in the image, where average slope and average point values would be mistaken

3. Suggest possible improvements to your pipeline

For the moment i can not suggest any improvement, but i know it needs to be improved :)

Thanks,
-Celal Unver.
