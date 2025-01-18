# Windowing
Manages or manipulates a signal or data sequence in segments, involves multiplying a signal by a "window function", which is a mathematical function that tapers the edges of the segment.

Windowing is crucial when dealing with finite-length signals or signals with discontinuities. Without windowing, operations like Fourier transforms or convolution might suffer from spectral leakage or discontinuities at the edges of the signal. Windowing is applied to limit the signal's boundaries smoothly, reducing unwanted artifacts when transforming or analyzing the signal.

**Spectral Leakage:** Happens when the signal's first and last value in the given time interval are not matching, which will result in a false assumption that the signal is periodic outside the window.

## Definition of Window Functions
Mathematical function applied to a segment of a signal to smooth or taper it. The window reduces the abrupt transitions at the edges of a finite signal, limiting high-frequency noise and improving the frequency-domain representation of the signal.

$f_{windowed} = f(t) • h(t)$ or $f_{windowed} = f[n] • h[n]$

## The Rectangular Window
The rectangular window is the simplest form of window function where $h(t)$ is 1 over the interval of intereset and 0 elsewhere. The sharp transitions at the window edges create high-frequency components in the frequency domain, causing the energy of the signal to "leak" into adjacent frequencies. The rectangular window has a very wide main lobe in its frequency response, reducing the ability to distinguish closely spaced frequencies.

**Smooth Edges -> Reduced Spectral Leakage**
**Wide Lobe -> Ability to distinguish close frequencies**

## The points of view of window function construction
- **Main Lobe Width:** Narrow main lobes help in resolving closely spaced frequencies.
- **Side Lobe Amplitude:** Lower side lobes reduce spectral leakage.
- **Computational Complexity:** Some windows are easier to compute than others.
- **Time-Domain Effects:** The shape of the window influences how the signal is "cut off" at the edges.

## The Triangular Window
A simple window function that starts at 0 and rises to 1 at the center of the window then falls back to 0 at the other edge. A triangular window is often created by taking the convolution of two rectangular windows.

#### Properties:
- **Time Domain:** The signal is tapered smoothly at both ends, reducing the abrupt cut-off.
- **Frequency Domain:** The triangular window has a main lobe that is wider than in case of rectangular window, with reduced side lobes, although the side lobes still exist.
- **Spectral Leakage:** Less spectral leakage compared to the rectangular window.

## Hahn Window
A cosine-shaped window that smooths the signal with a sinusoidal taper in time domain. In spectrum its shift of sinc function.

$h[n] = 0.5 \left( 1 - \cos \left( \frac{2\pi n}{N-1} \right) \right)$

#### Properties:
- **Time Domain:** The window smoothly starts and ends with zero, reducing the signal's discontinuities at the boundaries.
- **Frequency Domain:** The Hahn window has a wider main lobe and much smaller side lobes compared to the rectangular window, leading to significantly less spectral leakage.
- **Spectral Leakage:** The Hahn window reduces leakage even more than the triangular window due to the cosine taper.
- **Resolution:** The trade-off is that the main lobe is wider than the rectangular window, reducing the ability to distinguish closely spaced frequencies.
