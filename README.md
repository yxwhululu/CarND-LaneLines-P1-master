# CarND-LaneLines-P1-master
Finding Lane Lines on the Road
Finding Lane Lines on the Road
________________________________________
Finding Lane Lines on the Road
The goals / steps of this project are the following:
•	Make a pipeline that finds lane lines on the road
•	Reflect on your work in a written report
________________________________________
Reflection
1. My pipeline. 
My pipeline consisted of 5 steps.
Step1, I converted the images to grayscale;
Step2, I made the edge detection;
Step3,I set the ROI;
Step4,Detecting the lines with Hough transform；
Step5,Show the lines on the image.

为了在左右车道画一条线，我通过以下方法修改了draw_lines()这个函数：
In order to draw a single line on the left and right lanes, I modified the draw_lines() function by the method below:
第一步：假设左右车道线分别拥有相似的特征（斜率和截距），计算斜率和平均位置；
Step1, Assuming the left lane and right lane have the lines with similar features(slope and position) respectively , calculate the value of slope and average position.
第二步：为了剔除伪线条和线条晃动，计算所有直线的均值和方差，去除奇怪的直线。
Step2，To Removing spurious lines and lane shakiness，calculate the mean value and variance of the slope of the lines, get rid of the odd lines;
第三步：计算斜率和位置的均值以得到一条直线。
Step3,calculate the average of the slope and position to get one line;
第四步：计算直线的底部和顶部的点，然后画出这条线，左右车道线的流程一样。
Step4,calculate the bottom point and top point of the line, then draw the line;
The left lane and the right line use the same pipeline.

In video test, to the frames of the video, I used the same pipeline as in the image test .

2. The potential shortcomings with my current pipeline
One potential shortcoming:
If the road is curving, the line detecting maybe not ok.
 Another shortcoming:
If the ROI is set to be too large, some horizontal line is detected, such as the  edge of the car’s rear or the edge of the tree’s shape.
Third shortcoming:
I think if there is water on the road，the lanes’ feature will be weakened.
3. Possible improvements to my pipeline
To the above three shortcomings, the possible improvement would be:
1. If the road is curving, I think the curve fitting method should be used.
2.Before detecting the lines, maybe I should detected the cars in the ROI and erase them.
3.To the water problem, maybe we should do some work such as edge enhancement, but that may cause other problems.
