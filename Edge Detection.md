# Edge Detection
Edge detection is a technique in image processing that aims to identify the boundaries or edges of objects within an image. Edges represent significant transitions in intensity or color and often correspond to object boundaries.

## The Role of the Derivative
Edges are identified as regions in the image where the intensity of pixels changes sharply, such as transitioning from dark to light.

### Edge types
- **Step Edge:** A sudden change in intensity from one region to another.
- **Ramp Edge:** A gradual transition between regions.
- **Roof Edge:** A smooth transition in both directions.

The derivative of an image indicates the rate of change in intensity. The first derivative is used to identify areas of rapid intensity change, which correspond to edges. The second derivative can be used to identify the location of the edge (where the rate of change shifts).

## Gradient
The gradient of an image is a vector field that points in the direction of the greatest rate of increase in intensity, and its magnitude is the rate of change. Gradient-based  edge detection can highlight string edges. Usually computed with kernels like Sobel or Prewitt.

**Sobel:**
$$
\begin{bmatrix}
-1 & 0 & 1 \\
-2 & 0 & 2 \\
-1 & 0 & 1
\end{bmatrix}
$$
