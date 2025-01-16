# Simple Transforms

## Rotation
Rotation transforms an image or signal by turning it around a foxed point, usually the center. This is a geometric transformation that involves a matrix operation to map input coordinates to new rotated coordinates.

When applied to an image, each pixel is repositioned and new pixel values are computed at non-integer coordinates using interpolation methods like bilinear or bicubic interpolation. Rotation often introduces artifacts such as aliasing or jagged edges, especially for high-frequency content.

## Bilinear Interpolation
Estimates the value of a pixel at a non-integer position by linearly inteprolating along two dimensions. It uses the nearest 2x2 pixel grid surrounding the target position.

Estimates a new pixel value using the distance-weighted average of the four closest pixels.

Frequently used in scaling, rotation and other affine transformations.

## Bicubic Interpolation
Extends bilinear interpolation by considering the values of the 16 nearest pixels (4x4 grid) to estimate the pixel value. It involves cubic polynomials in both horizontal and vertical dimensions.

Produces smoother and more visually appealing results compared to bilinear interpolation. More computationally expensive and may introduce ringing artifacts near sharp transitions (edges)

## Transforms of the intensity function
The intensity function refers to the grayscale level or brightness of pixels in an image. It represents the magnitude of light (brightness) at each pixel and is typically denoted as $I(x, y)$.

For grayscale images $I(x, y)$ is typically a scalar value in a range, such as [0, 255] for 8-bit images. In color images, the intensity is often split into three separate components corresponding to the red, green and blue (RGB) channels.

Intensity transformations involve modifying the pixel values of the image to achieve a desired effect.

#### Point Transforms:
Point transforms operate on each pixel independently.
- **Linear Transformation:** Brightness adjustment (via b) and contrast scaling (via a). $I'(x, y) = a * I(x, y) + b$
- **Gamma Correction:** Adjust the contrast for images with non-linear intensity distributions. $I'(x, y) = c * I(x, y)^γ$
- **Logarithmic Transform:** Enhance low-intensity values. $I'(x, y) = c * log(1 + I(x, y))$
- **Exponential Transform:** Enhance high-intensity values. $I'(x, y) = c * (e^{I(x, y)} - 1)$
  
## Histogram equalization
