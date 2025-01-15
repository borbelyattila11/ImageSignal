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

## Laplace (Laplacian Operator):
The Laplacian is a second-order derivative and it can detect areas where the intensity changes most abruptly. It is sensitive to noise so it is often combined with smoothing.

## Examples of Simple Kernels
- **Sobel:** A simple edge detection operator that computes the gradient of the image. It uses a pair of 3x3 convolution kernels to estimate the gradient in the x and y directions.
- **Prewitt:** Similiar to Sobel but with a slightly different kernel.
- **Laplace:** The Laplacian mask is typically a 3x3 kernel used to calculate the second derivative. Can identify areas where the intensity of the image changes most dramatically.

## How to treat noise
Noise it typically present in images and can interfere with edge detection. To mitigate noise, its common to smooth the image before applying edge detection. This can be done using filters like the Gaussian blur, which removes high-frequency noise while preserving edges.

## The LoG transform (Laplacian of Gaussian)
Combines Gaussian smoothing with the Laplacian operator. First it applies the Gaussian filter to smooth the image, which reduces noise and avoid false edge detection. In the Gaussian filter the **σ** is the standard deviation that controls the level of smoothing. Second the Laplacian operator to detect edges based on changes in intensity, resulting in zero-crossing in the second derivative. This method is more effective than just using the Laplacian itself.

**Zero-crossing** refers to a point where the value of the second derivative of a function changes sign.

## The Marr-Hildreth
The algorithm's goal is to detect the **zero-crossings** of the LoG, which corresponds to the locations of edges in an image. First step of the algorithm is to apply LoG on the image. In addition to applying the LoG operator it focuses on detecting zero-crossings. May produce false edges.

## The Canny

## The Hough-transform
