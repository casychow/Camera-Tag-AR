# Camera Tag-Based Augmented Reality
There are three parts to this project:
1. Find Vanishing Points
2. Camera Calibration
3. Render Aruco Tag Generated AR Box

### Final Result
![](https://i.imgur.com/y8FvYQY.jpg)


## Part 1 - Find Vanishing Points
First, the coordinates of the picture origin and vanishing points were manually detected and recorded. The points were then used to compute an `A` and `b` matrix that would be used to solve the equation `Ax=b`. The resulting 2x1 vector `x`, would represent `x0`and `y0`, the principal point. The equations are represented below.

![](https://i.imgur.com/535yLsw.png)

The focal point was found using using the following equation.
![](https://i.imgur.com/32SKRy4.png)

The blue circles represent the intersection of vanishing lines, or in other words, the vanishing points.
![](https://i.imgur.com/c480MTg.png)


## Part 2 - Camera Calibration
This part of the project used the Aruco tags found in the `cv2` Python library. One must generate a chessboard of Aruco tags as shown below, take pictures of the Arcuo chessboard with varying distance and angles with respect to the chessboard, and pass all images into this program to calibrate the camera.

The pictures used to calibrate the camera are placed in the `calibration_pics` folder.

## Part 3 - Render Aruco Tag Generated AR Box
After the camera has been calibrated, the same camera should be used to take one picture of an Aruco tag. We will project a cube on top of the tag, as shown below.

![](https://i.imgur.com/JQYlUJR.jpg)
