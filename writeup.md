# **Finding Lane Lines on the Road** , Reflection

## 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline basically consists of 5 steps.
First, I converted the images to grayscale, then I added Gaussian blur for better generalization.
After Canny edge detection, I cut the specific lower area because we can use heuristics.
Finally, Hough transform was added.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function.
Firstly, to separate left lines with right ones, I used the angle of line.
Then to each group, weighted average was calculated to decide the best line.

Initially my pipeline didn't work well for optional challenge.
By limiting the range of angle, I could get better generalization.

## 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when I run the code at practical environment.
Pure python is mainly used in my implementation.
Current FPS is relatively slow.

## 3. Suggest possible improvements to your pipeline

A possible improvement would be to use the library like numpy effectively.
If I search well, there might be more efficient matrix calculation.
