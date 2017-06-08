
#**Finding Lane Lines on the Road** 

Reflection
###1. Pipeline description.
The pipeline consists of 8 basic steps.

####Step 1. Input.


<img src="https://github.com/MariaSkr/CarND-LaneLines-P1/blob/master/test_images/solidWhiteRight.jpg" width="480" alt="Combined Image" />





####Step 2. Apply the Grayscale transform.

<img src="https://github.com/MariaSkr/CarND-LaneLines-P1/blob/master/test_images/output_solidWhiteRightgray.jpg" width="480" alt="Combined Image" />




####Step 3. Apply Gaussian smoothing.


<img src="https://github.com/MariaSkr/CarND-LaneLines-P1/blob/master/test_images/output_solidWhiteRightgaussian_blur.jpg"  width="480" alt="Combined Image" />




####Step 4. Apply the Canny transform.
Canny transform used to find the edges of the lane lines in an image of the road.

<img src="https://github.com/MariaSkr/CarND-LaneLines-P1/blob/master/test_images/output_solidWhiteRightedges.jpg"  width="480" alt="Combined Image" />



####Step 5. Region masking.

<img src="https://github.com/MariaSkr/CarND-LaneLines-P1/blob/master/test_images/output_solidWhiteRighttarget.jpg" width="480" alt="Combined Image" />



####Step 6. Define the Hough transform parameters and run Hough on edge detected image.

<img src="https://github.com/MariaSkr/CarND-LaneLines-P1/blob/master/test_images/output_solidWhiteRighthough_lines.jpg" width="480" alt="Combined Image" />



####Step 7 Separate lines by slope.
m = (Y2 - Y1) / (X2 - X1). I am going to use this equation to organize lines by their slope. It is important to point out that the y-axis is inverted in OpenCV when reading images, so positive slopes will be the right lane and negative slopes will be the left lane. 

####Step 8 Extending Hough Lines into a Single Unified Lane.

Now I need to piece together lines and unify them into the best estimate for the lane line location. For this:
1) Line outliers are removed (e.g flat lines or lines that deviate significantly from the man)
2) Lines are merged by the mean of their endpoints. 
3) Endpoints are extended off the image canvas. 


###3. Possible improvements to the pipeline
A possible improvements:
 Create a color mask that will highlights the whites and yellows in the frame. This will ensure our Hough lines are more easily detected in shaded regions or low contrast regions.


