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
Designed to identify significant edges, preserve them well and eliminate noise that might interfere with the edge detection process.

### Steps
1. **Noise Reduction (Gaussian filtering):** Apply Gaussian smoothing to reduce noise and fine details. The image is convolved with a Gaussian kernel to blur the image. The amount of smoothing is controlled by the standard deviation (σ) of the Gaussian kernel.
2. **Gradient Calculation (Edge Strength and Direction):** After smoothing compute the gradient magnitude and gradient direction of the image, this typically done by the Sobel operator.
  - The **gradient magnitude** (G) at each pixel is calculated as the squared root of G_x and G_y, which will give the strength of the edge at each pixel.
  - The **gradient direction** (θ) at each pixel is calculated as the atan2(G_y, G_x), which represents the orientation of the edge at that point.
3. **Non-Maximum Suppression (Edge Thinning):** The goal is to thin out the edges by suppressing non-maximum values in the gradient magnitude image. Each pixel is examined along the direction of the gradient and check wether the pixel is the local maximum in that direction, in case it is not the local maximum the pixel is suppressed (set to zero).
4. **Double Thresholding (Edge Classification):** After non-maximum suppression the gradient magnitudes are thresholded into three categories:
    - **Strong edges:** Pixels with gradient magnitudes above a high threshold are considered strong edges.
    - **Weak edges:** Pixel with gradient magnitudes between high and low tresholds are considered weak edges.
    - **Non-edges:** Pixels with gradient magnitudes below the low threshold are discarded.
The high and low tresholds are typically set as a percentage of the maximum gradient value in the image.
5. **Edge Tracking:** The final step is to link weak edges to strong edges based on their proximity. For each weak edge pixel, check if it connected to any strong edge pixels. If a weak edge pixel has at least one strong edge pixel as neighbor, it is kept as part of the edge. if a weak edge pixel is not connected to any strong edge pixel, it is discarded. It ensures that weak edges which are part of the actual object boundary are connected and included in the final edge map.

## The Hough-transform
