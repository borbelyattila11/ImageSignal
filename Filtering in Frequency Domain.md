# Filtering in Frequency Domain
Refers to the process of modifying an image's frequency components in order to enhance or suppress certain aspects. Often used to improve image quality by removing unwanted noise or emphasizing specific features.

## The General Model
Transforming the image from spatial domain (pixel values) to frequency domain (sinusoidal patterns) using Fourier Transform. In the frequency domain the image is represented by spectrum and phase (frequency spectrum).

## Fourier-Transform of images
The Fourier Transform (Discrete Fourier Transform for images) decomposes the image into a sum of sine and cosine waves, each with specific frequencies and amplitudes. In case of images 2D FT is commonly used, and for transforming the image back into spatial domain Inverse Fourier Transform can be applied.

Low-Frequency components are not automatically centered in the output, by default the zero-frequency appears at the top-left corner of the frequency spectrum. High-Frequency components are distributed along the edges, further away from the origin. To center the low-frequency components we need to perform a frequency shift (Multiply the input image by (-1)^x+y before applying FT).

#### Frequency Spectrum
Shows how different spatial frequencies contribute to an image. For a 2D image the frequency spectrum is often visualized as in intensity map where the center represents the low-frequencies and the edges represent the high-frequencies.

## Spectrum, Phase (Frequency Components)
- **Spectrum:** Refers to the magnitudes of the frequency components, it represents how much of a particular frequency is present in the image (Describes how the energy of an image is distributed across different frequencies).
- **Phase:** Contains information about the position of structures (like edges and textures) in the spatial domain. The phase tells where that frequency occurs in the image.

While the magnitude of a frequency component (spectrum) describes 

## Which type of noise can be detected, filtered?

## Applications
