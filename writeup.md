# **Finding Lane Lines on the Road** 

## Writeup

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

### 1. draw_lines() function modifications

First of all, I followed [these suggestion](https://knowledge.udacity.com/questions/18578) but I wasn't satisfied with
the result. So, I took a different approach by taking the mean of the slopes and coefficient of all the line found.
In order to filter some noise, I took only the slopes that where in a range of values. After that, I calculated two points and used them to draw the line.

The steps are the following:

1. calculate slope and coefficient of the line
2. filter the slope
3. divide the slope for line on the left and line on the right of the image (using slope's sign)
4. take the mean of slope and coefficient and use them to draw the left and right lines

### 2. My pipeline

In order to try to improve performance, I switched from using grayscale images to using HSV, which is more robust
in situations where illumination changes. Aside from converting to hsv and filtering by colors, the pipeline resemble
the one seen in the course material.

### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use lines fuond in the previous images to smooth the behavior of the line, which have some kind of jitter. Furthermore, a better filtering (by tuning even more Gaussian. Canny and Hough parameters) would improve the lane finding. Finally, some more filtering, maybe by using outlier's detection, could be possible in order to make the pipeline more robust to noise.
