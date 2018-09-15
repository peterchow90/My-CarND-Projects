---
## 1st. compute the camera calibration using chessboard images
![drawCorners](output_images/drawCorners.png)

---
## 2nd. Apply a distortion correction to raw images
* use objpoints and imgpoints caculated in above cell
* skip calibrateCamera calculation once the data is ready to improve perfomace
![distored_vs_undistored](output_images/distored_vs_undistored.png)

---
## 3rd.  Create a thresholded binary image
* use sobel operator to creat a horizonal direction binary image
* use magnitude threshold filter to creat a binary image
* use gradient direction threshold filter to creat binary image
* use channel S of color space HLS to filter to get a binary image
![sobel_x_vs_magnitude](output_images/sobel_x_vs_magnitude.png)
![direction_vs_HLS-S-apace](output_images/direction_vs_HLS-S-apace.png)

---
## 4th. Apply a perspective transform to rectify binary image ("birds-eye view")
* wrap image
* combine threshold and wrap functions as a whole
![combin_x-s_vs_wraped-image](output_images/combin_x-s_vs_wraped-image.png)

---
## 5th. Detect lane pixels and fit to find the lane boundary
* firstly, use window histgram to search the lane line in a wrapped and thresholded image
* when got a efficient lane line, next frames can be detected simply
![wraped-image_vs_lane-detected-image](output_images/wraped-image_vs_lane-detected-image.png)

---
## 6th. Determine the curvature of the lane and vehicle position with respect to center
* sannity check with left and right lines
* write text to image upper left
* calculate curvature
* draw line on image and wrap back to source image
![drawLines_writeText2Image](output_images/drawLines_writeText2Image.png)