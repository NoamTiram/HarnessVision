# HarnessVision

Optical low is the pattern of apparent motion of image objects between two consecutive frames caused by the movement of object or camera.
Optical Flow assumptions:
  1.	Pixel intensities of an object do not change between consecutive frames (i.e same light)
  2.	Neighboring pixels have similar motion (not a random simple point moving)

In python OpenCV, We can have two methods:
  1.	Sparse: Provide the frame, the points to track and the next frame (Lucas-Kanade method) 
    a.	Choose manually 
    b.	Use Object detection 
  2.	Dense: track all the points – using Gunner Franeback’s algorithm. We are using that method.

In the algorithm, I'm converting optical flow vector into a polar form, then use the diff of the total magnitude between two consecutive frames (which being normalized into 0-255, just for faster calculations) in order to determine the intense of the movement. 
I'm normalizing by precentage of "high movements" (alpha param) - and that's the score. that way, long/short videos won't be biased.

for visualizations, plotMov() is printing the movements during the video (y axis) along the frames (x axis)

