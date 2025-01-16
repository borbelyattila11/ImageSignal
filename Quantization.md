# Quantization
By sampling a continous signal converted to discrete signal (discrete in time but continous in amplitde), the amplitude of the signal at each sampled point is approximated by a discrete value. Quantization rounds or maps these continous amplitude values of the signal to the nearest discrete values in a predefined range (represented by a fixed number of bits).

## Linear Quantization
In linear quantization the intervals between quantization levels are equal, which is best suited for uniformly distributed signals. May lead to high quantization error for signals with large amplitude variations.

## Non-Linear Quantization
Non-linear quantization uses intervals that vary in size, which aligns better with statistical distribution of certain signals, such as speech or audio. Smaller intervals are used for frequently occuring amplitudes, and larger intervals are used for rarer values. Logarithmic Quantization assigns small and more levels to low-frequency values and fewer but wider levels to high-frequency ones. For speech non-linear quantization is used because of the Bark Scale (non-linear too).

## Quantization as a Compression Technique
Quantization is a key element of lossy compression algorithms, where reducing the number of levels decreases the amount of data to store or transmit. While quantization introduces errors, these are often negligible.

## Logarithmic Quantization in the Telephone Standard: Companders
In telecommunications **logarithmic quantization** is commonly implemented using companding (compressing + expanding):
- **Compression:** Reduces the amplitude range of the input signal using a logarithmic function (μ-law or A-law)
- **Expansion:** Restores the signal to its original amplitude range on the receiver side.

#### μ-law Companding
Where μ is a parameter that determines the amount of compression and x is the normalized signal amplitude (-1 <= x <= 1).

$F(x) = \text{sign}(x) \cdot \frac{\ln(1 + \mu|x|)}{\ln(1 + \mu)}$

Signals, especially weaker ones, can be masked by noise during transmission or storage. Companding mitigates this issue by amplifying weaker signals during compression and restoring them afterward.

Reduces quantization noise for small signals, improves signal-to-noise ratio for low-amplitude audio.

## The Role of Quantization in JPEG Image Compression
JPEG uses quantization in its lossy compression pipeline:
1. **Transform:** The image is divided into blocks, and a Discrete Cosine Transform is applied.
2. **Quantization:** DCT coefficients are divided by a quantization matrix (luminance table, chrominance table) and rounded to the nearest integer. High-frequency components are significantly reduced, preserving only visually significant low-frequency information.
3. **Entropy Coding:** The quantized coefficients are encoded using Huffman coding or RLE.
