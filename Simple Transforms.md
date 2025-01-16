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

## Histogram equalization
