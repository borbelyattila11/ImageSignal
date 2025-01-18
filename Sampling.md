# Sampling
Process of converting continous analog signals into discrete digital signals, involves sampling the continous signal at discrete time intervals and quantizing the amplitude of the samples.

## Uniform Sampling
Refers to sampling at equally spaced time intervals, most common form of sampling used in signal processing, where each sample is taken at the same time gap.

## The Effect of Sampling in the Frequency Domain
Sampling in the frequency domain results in the periodic repetition of the signal's spectrum at multiples of the sampling frequency, causing overlapping or "folding" of higher frequencies into lower ones. This repetition occurs due to the convolution of the original spectrum with a series of spikes from the Dirac comb. The Dirac comb is used to model periodic sampling, as it picks out values of a signal at regular time intervals.

## Aliasing
Occurs when a signal is undersampled and higher-frequency components of the signal are incorrectly mapped to lower frequencies. This results in a distortion of the signal, which can be avoided by ensuring the sampling rate is suefficiently high (oversampled).

Aliasing occurs when the sampling frequency $f_s$ is not high enough for capture all the frequency components of the original signal. $f_s > 2f_max$

- **Rate of Distortion:** How much the reconstructed signal differs from the original continous-time signal due to aliasing effects. This distortion occurs when a signal is sampled below the Nyquist rate and high-frequency components in the original signal "fold" back into lower-frequencies in the sampled signal.

## The Nyquist Frequency
The Nyquist Frequency is the highest frequency that can be accurately sampled without aliasing, it is equal to half of the sampling rate. To avoid aliasing the sampling rate must be at least twice the highest frequency present in the signal.

## Antialias filters
- **Analog Antialias filters:** These are low-pass filters applied to a continuous-time signal before it is sampled. Their purpose is to remove high-frequency components from the signal, preventing aliasing when the signal is discretized (sampled). They ensure that the signal's frequency components remain below the Nyquist frequency (half of the sampling rate) before sampling. Example: RC Low-Pass Filter, Butterworth
- **Discrete Antialias filters:** These are filters applied after sampling, typically designed to remove high-frequency components that are above the Nyquist frequency of the discretized signal. A Finite Impulse Response (FIR) or Infinite Impulse Response (IIR) filter can be used to filter out these high-frequency components, reducing the risk of aliasing when downsampling.
