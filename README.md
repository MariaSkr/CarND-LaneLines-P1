
#**Finding Lane Lines on the Road** 

Reflection
###1. Pipeline description.
The pipeline consists of 7 basic steps.

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



####Step 7 Finding Lane Lines on the Road.


<img src="https://github.com/MariaSkr/CarND-LaneLines-P1/blob/master/test_images/output_correct1.jpg" width="480" alt="Combined Image" />


###3. Possible improvements to the pipeline
A possible improvements:
 Create a color mask that will highlights the whites and yellows in the frame. This will ensure our Hough lines are more easily detected in shaded regions or low contrast regions.


