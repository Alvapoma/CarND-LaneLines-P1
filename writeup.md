# **Finding Lane Lines on the Road** 

## introduction

### the proyect consist on find the lanes lines on the road using Opencv and python in a video file

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Steps

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

### 1. Get the image from video  and procces the image 
Use a Gausian filter 
for the moment not apply the color selection using RGB
![alt text][image1]
### 2. Region Masking 

cut only the lane, for only focus on a specific region on an image, 

### 3. Canny detection

Find edges by looking for strong gradient, very different  values  between adjancent pixels

edgets = cv2.Canny(gray , low_threshold , high_threshold)

### 4. Hough Transform 

get the lines 

lines = cv2.Houghlines( image, rho, theta, threshold)

image: source image 
lines: Output  vector of lines, 

rho: Distance resolution of the accumulator in pixeles 
theta: Angle resolution of the accumulator in radians

threshold: Accumulator threshold parameter. Only those lines are returned that get enough votes (>threshold).

### 5. Proces the line  for get a line on each carrier 

for get the tow lines of a carrier, filter the lines for angle for get the right and lef lines ang get only when there ara more that 45 grades for minimiset the noise with the short  lines with others objects on the road.

y=mx+b
we get the centroid of  m  and  b for the right line and the left line. and use for get value of  (x0,y0) and (x1,y1) where y0 is 0 and y1 is height of image.

## Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when there are other objects on the roads and the algorit confusem for example  with the  

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to kalman filter for try predict  the broken line  when the kalman line dont  oget a line 

test with probabilistic hough lines 


Another potential improvement could be to ...
