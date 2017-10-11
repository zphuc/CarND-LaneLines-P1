# **"Finding Lane Lines on the Road" Report**
---

[//]: # (Image References)

---

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. 

1. Converted the images to grayscale
2. Applied Gaussian smoothing for each image
3. Applied Canny
4. Applied image mask

   Some tuning was done for vertices to obtain the good mask 
5. Run Hough on edge detected image

   Some tunning was done for the threshold, min_line_length and max_line_gap parameters.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by the following steps.

1. Extrapolate to the top and bottom of the lane.
2. Average the lines for the left line vs. the right line by their slope ((y2-y1)/(x2-x1))
   Moreover, I also adopted the ranges of the slopes from 15deg to 75deg to limit the error lines 


Follow images show results how the pipeline works.

Orginal image

<img src="test_images_out/s0.png" width="480" alt="Combined Image" />

Step1

<img src="test_images_out/s1.png" width="480" alt="Combined Image" />

Step2

<img src="test_images_out/s2.png" width="480" alt="Combined Image" />

Step3

<img src="test_images_out/s3.png" width="480" alt="Combined Image" />

Step4

<img src="test_images_out/s4.png" width="480" alt="Combined Image" />

Step5

<img src="test_images_out/s5.png" width="480" alt="Combined Image" />

Final Result

<img src="test_images_out/s6.png" width="480" alt="Combined Image" />

### 2. Identify potential shortcomings with your current pipeline

The parameters were not handly tunned well. 
Large errors were found for the "Optional challenge" video.  

### 3. Suggest possible improvements to your pipeline

Some automatic tuning on the parameters need to be done for each case.  
Another potential improvement could be done by ...

