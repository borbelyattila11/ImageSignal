# Filtering in Frequency Domain
Refers to the process of modifying an image's frequency components in order to enhance or suppress certain aspects. Often used to improve image quality by removing unwanted noise or emphasizing specific features.

## The General Model
Transforming the image from spatial domain (pixel values) to frequency domain (sinusoidal patterns) using Fourier Transform. In the frequency domain the image is represented by amplitude and phase (frequency spectrum).

## Fourier-Transform of images
The Fourier Transform (Discrete Fourier Transform for images) decomposes the image into a sum of sine and cosine waves, each with specific frequencies and amplitudes. In case of images 2D FT is commonly used, and for transforming the image back into spatial domain Inverse Fourier Transform can be applied.

Low-Frequency components are not automatically centered in the output, by default the zero-frequency appears at the top-left corner of the frequency spectrum. High-Frequency components are distributed along the edges, further away from the origin. To center the low-frequency components we need to perform a frequency shift (Multiply the input image by (-1)^x+y before applying FT).

#### Frequency Spectrum
Shows how different spatial frequencies contribute to an image. For a 2D image the frequency spectrum is often visualized as in intensity map where the center represents the low-frequencies and the edges represent the high-frequencies.

## Spectrum, Phase (Frequency Components)
- **Amplitude:** Describes how the energy of an image is distributed across different frequencies.
- **Phase:** The phase tells us where a specific frequency occurs in the iage and contributes to the spatial arrangement of structures like edges, textures and details.

While the magnitude of a frequency component (spectrum) describes how strong a certain frequency is, the phase tells where that frequency occurs in the image.

## Which type of noise can be detected, filtered?

1. **Gaussian Noise:** Often appears as random fluctuations, typically present across all frequencies, but more prominent to high-frequencies.
2. **Salt-Pepper Noise:** Usually concentrated in the higher frequencies and can be filtered using low-pass filters.
3. **Poisson Noise:** Happens particularly in low-light conditions, requires specialized frequency domain techniques.
4. **Periodic Noise:** Appears in a regular, repeating pattern, can be detected as spikes at specific frequencies and can be removed by filtering out those frequencies.

## Applications
- **Noise Reduction:** Filtering high-frequency noise using low-pass filteres or removing periodic noise using band-stop filters.
- **Image Enhancement:** Emphasizing certain frequencies to enhance freatures like edges.
- **Compression:** By discarding high-frequency components, which often represent noise or finer details, image compression algorithms can reduce file size.
- **Edge Detection:** High-pass filtering can be used to enhance edges in an image, useful in object detection and analysis.
