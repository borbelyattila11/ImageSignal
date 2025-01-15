# Filtering in Space Domain
Applying a filter (kernel or mask) to an image in such a way that the filter interacts with the spatial distribution of pixel values in the image.

## Concept
Spatial filtering involves processing an image by manipulating the pixel values of each pixel based on its neighbors. A filter typically a small matrix (3x3, 5x5) that slid over the entire image (convolution). The value of each pixel in the output image is calculated based on the weighted sum of the corresponding pixel and its neighbors in the input image.

## Types of Filters:
- **Linear:** These filters compute the output pixel by applying a linear combination of neighboring pixels.
  - **Smoothing (Blurring):** Reduces noise or detail by averaging pixel values in the neighborhood (Gaussian blur).
  - **Edge Detection:** Detects edges by highlighting areas of rapid intensity change (Sobel, Prewitt)
- **Non-Linear:** These filters compute the output pixel using a non-linear combination of neighboring pixels.
  - **Median filter:** Replaces the pixel value with the median of the neighboring pixels, often used for removing salt-and-pepper noise.
 
## Image Sharpening (Gradient, Laplace operator)
Image sharpening is a technique used to enhance the details and edges in an image. Uses operators like Gradient and Laplacian to highlight changes in intensity, which can sharpen the image.

### Gradient-based Sharpening
The gradient of an image represents the rate of change of pixel intensities, and it is often used to detect edges in an image. The gradient is computed using convolution with kernels like the **Sobel** or **Prewitt** operators.

**Sobel Operator:** Computes the gradient in the horizontal and vertical directions.

For sharpening, we focus on the high-frequency components (edges), so a simple approach is to subtract the smoothed version of the image (Gaussian blur) from the original image to enhance the edges.

$I_{sharpened} = I - \alpha \cdot \nabla I$

where:
- $I$ is the original image
- $\alpha$ is a scalar to control the sharpening strength
- $\nabla I$ is the gradient (magnitude)

### Laplacian-based Sharpening
The Laplacian is a second-order derivative operator that highlights regions of rapid intensity change (edge and noise).

**Laplacian Operator:** Highlights areas with high-frequency content (edges), for sharpening we can subtract the Laplacian of an image from the original image to enhance edges.

$I_{sharpened} = I - \alpha \cdot \nabla I$

where:
- $I$ is the original image
- $\alpha$ is a scalar to control the sharpening strength
- $\nabla I$ is the Laplacian of the image

Alternatively, we can add the Laplacian result to the original image to sharpen it:

$I_{sharpened} = I + \alpha \cdot \nabla I$

## Applications
- Edge Detection
- Image Enhancement
- Image Compression
