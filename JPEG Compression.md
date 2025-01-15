# JPEG Compression

## JPEG (Joint Photographic Experts Group)
Algorithm for compressing still images, it is lossy compression method, some of the data is discarded to reduce file size.

## Human Vision Sensitivity
The human vision is more sensitive to low-frequency details (smooth regions and gradual changes) than to high-frequency details (sharp edges, textures or noise). JPEG uses this behavior, since the image's energy is concentrated in the low-frequency components making it possible to compress the high-frequency ones more aggressively.

## JPEG Algorithm
- Compression efficiency: reduces file size
- Perceptual Quality: the compressed image still look similiar to the original to the human eye
- Speed: compress and decompress quickly enough for practical use
- Lossy Nature: sacrifices some image data to achieve compression (quantization)

### Steps
1. Color Space Transformation: RGB to YCbCr
2. Subsampling: Reduce the resolution of chrominance components (Cb and Cr) (4:2:0)
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

## The Discrete Cosine Transform (DCT)
**DCT** Discrete Cosine Transform (DCT) applied to 8x8 blocks in the JPEG algorithm. It converts spatial-domain pixel values into frequency-domain coefficients. The higher frequencies, which correspind to fine details are typically quantized more aggressively, leading to compression.

## Quantization
Quantization reduces the precision of the DCT coefficients by dividing them element-wise by a predefined **quantization table** and rounding the results. This step introduces loss but essential for achieving significant compression.

- **Luminance Table**: Used for the Y (brightness) component
- **Chrominance Table**: Used for the Cb and Cr (color) components

The quantization tables specify how much each frequency component should be scaled based on the human visual system:
- Low-frequency components have smaller values in the table and are preseved with higher precison (general structure of the image)
- High-frequency components have larger values in the table, so they are more aggressively quantized (details and sharp changes)

## Zig-Zag Ordering
After quantization, the DCT coefficients are reordered using **zig-zag scanning**, it reorders the coefficients by starting at the top-left corner of the 8x8 block and moving in a zig-zag pattern, collecting the coefficients in the order of their frequency. This helps grouping low-frequency components (since they are more important) before high-frequency ones (they are discardables).

The DCT compacts most of the energy of the image into the **low-frequency** components, which are located in the top-left corner of the DCT matrix. The **high-frequency** components are located in the bottom-right corner, typically contain much less energy and often become zero after quantization.

By zig-zag ordering the coefficients the most important and non-zero values are placed first in teh sequence. This increases the efficiency of the entropy coding, because the long runs of zeros are grouped together at the end, making them easier to compress using run-length encoding (RLE).

## Notes:
- **4:2:0 subsampling ratio:** The 4:2:0 chroma subsampling ratio is widely used in image and video compression because it effectively reduces data size while maintaining good visual quality. For every 4 luminance samples there are 2 chrominance samples in the horizontal direction and no additional samples in the vertical direction for the same block.
