# JPEG Compression

## JPEG (Joint Photographic Experts Group)
Algorithm for compressing still images, it is lossy compression method, some of the data is discarded to reduce file size.

## JPEG Algorithm
- Compression efficiency: reduces file size
- Perceptual Quality: the compressed image still look similiar to the original to the human eye
- Speed: compress and decompress quickly enough for practical use
- Lossy Nature: sacrifices some image data to achieve compression (quantization)

### Steps
1. Color Space Transformation: RGB to YCbCr
2. Subsampling: Reduce the resolution of chrominance components (Cb and Cr)
3. Block Splitting: Divide the image into 8x8 blocks
4. Discrete Cosine Transform (DCT): Apply DCT to each block to convert spatial domain data to frequency domain
5. Quantization: Quantize the DCT coefficients to reduce precision and achieve compression
6. Zig-Zag Ordering: Reorganize the quantized coefficients in a zig-zag pattern
7. Entropy Coding: Apply RLE or Huffman coding to compress

## RBG-YCbCr Color Space Transform
The image is typically transformed from RGB color space to YCbCr. This transformation separates the luminance (Y) and chrominance (Cb and Cr) components.
- **Y** represents the brightness (luminance)
- **Cb** and **Cr** represents the chrominance (color information)
This separation helps compressing the chrominance components more heavily since the human eye is less sensitive to color details than brightness.

## The Modified Discretee Cosine Transform (MDCT)
**MDCT** is a variant of Discrete Cosine Transform (DCT) applied to 8x8 blocks in the JPEG algorithm. It converts spatial-domain pixel values into frequency-domain coefficients. The higher frequencies, which correspind to fine details are typically quantized more aggressively, leading to compression.

## Quantization
In JPEG the process of reducing precision of the DCT coefficients. A **quantization matrix** is used to divide each DCT coefficient by a corresponding value, rounding it to an integer. This introduces loss, but also significantly reduces the data size.

## Zig-Zag Ordering
After quantization, the DCT coefficients are reordered using **zig-zag scanning**, it reorders the coefficients by starting at the top-left corner of the 8x8 block and moving in a zig-zag pattern, collecting the coefficients in the order of their frequency. This helps grouping low-frequency components (since they are more important) before high-frequency ones (they are discardables).
