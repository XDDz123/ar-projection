# AR Projection
This project implements AR features for projecting 3D shapes onto video footage with square trackers. </br></br>
The program first locates the corners of the square trackers as markers using the [condensation algorithm](https://en.wikipedia.org/wiki/Condensation_algorithm).</br>
The marker positions are used for pose estimation. </br>
Specifically, the homography, rotation, and translation matrices are estimated to determine the state of the transformation matrix. </br>
The transformation matrix enables the conversion between screen-space pixel positions and 3D coordinates.  </br>
With this 3D shapes could be projected into the 2D footage.

## Libraries
* numpy
* scipy.io
* scipt.sp
* cv2
* os
* pylab
  
## Sample Output
![output](https://github.com/XDDz123/ar-projection/assets/20507222/553b696f-16fa-4ccd-86d8-590ca7fa8716)
