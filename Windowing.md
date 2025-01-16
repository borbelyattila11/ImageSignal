# Windowing
Manages or manipulates a signal or data sequence in segments, involves multiplying a signal by a "window function", which is a mathematical function that tapers the edges of the segment.

Windowing is crucial when dealing with finite-length signals or signals with discontinuities. Without windowing, operations like Fourier transforms or convolution might suffer from spectral leakage or discontinuities at the edges of the signal. Windowing is applied to limit the signal's boundaries smoothly, reducing unwanted artifacts when transforming or analyzing the signal.

## Definition of Window Functions
Mathematical function applied to a segment of a signal to smooth or taper it. The window reduces the abrupt transitions at the edges of a finite signal, limiting high-frequency noise and improving the frequency-domain representation of the signal.

$f_{windowed} = f(t) \dot h(t)$ or $f_{windowed} = f[n] \dot h[n]$
