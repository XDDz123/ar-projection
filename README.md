# AR Projection
This project implements AR features for projecting 3D shapes onto video footage with square trackers from scratch with Python. </br>

The process could be described as follows:
1. First locate the corners of the square tracker as markers using the [condensation algorithm](https://en.wikipedia.org/wiki/Condensation_algorithm). </br>
   The condensation algorithm performs factored sampling and resampling by leveraging Bayes rule $p(X|Z) = p(Z|X)p(X)$. </br>
   In general terms, it involves the following steps:</br>
   1. Randomly sample $N$ particles from the state of the previous time step $s_{t-1}^{(n)}$ based on a set of weights $\pi_{t-1}^{(n)}$. </br>
   2. Propagate particles with deterministic dynamics, then add perturbation. </br>
   This project utlilzes brownian motion to generate a set of particles $s_{t}^{(n)}$ in the new time step.
   3. Compute the likelihood for new samples $p(z_t | x_t)$. This can be done with template matching. </br>
   Then update and normalize the weights according to the computed likelihood $\pi_{t}^{(n)} = p(z_t | x_t)$.
2. Use the marker positions for pose estimation. </br> Specifically, the rotation, and translation matrices are estimated to determine the state of the extrinsic matrix. </br>
This matrix enables the conversion between screen-space pixel positions and 3D coordinates.  </br>
3. Perform nonlinear minimization on the estimated matrix to improve projection accuracy. </br>

With this 3D shapes could be projected into the 2D footage.

## Libraries
* numpy
* scipy.io
* scipy.sp
* cv2
* os
* pylab
  
## Sample Output
![output](https://github.com/XDDz123/ar-projection/assets/20507222/553b696f-16fa-4ccd-86d8-590ca7fa8716)
