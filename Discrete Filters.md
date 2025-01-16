# Discrete Filters
Discrete filters are filters that process discrete-time signals, these are often implemented using difference equations and are used in digital signal processing. There are two types of discrete filters: **FIR (Finite Impulse Response)** and **IIR (Infinite Impulse Response)**

## FIR (Finite Impulse Response)
They are characterized by having an impulse response that settles to zero in a finite amount of time.

#### Characteristics:
1. **Linearity:** The superposition principle applies, the response to a sum of inputs is the sum of their individual responses.
2. **Time-Invariance:** Their behavior doesn't change over time.
3. **Stability:** Inherently stable because they do not use feedback, stability ensures since the output is a weighted-sum of a infinite number of input samples.
4. **Causality:** Designed to be causal, which means the filter's output depends only on present and past inputs, it is a practical requirement for real-time systems.
5. **Phase:** Designed to have a linear phase, which means that all frequency components of the input signal are delayed by the same amount of time.

The output $y[n]$ of an FIR filter is a linear convolution of the input signal $x[n]$ with the filter's impulse response $h[n]$.

$y[n] = \sum_{k=0}^{M-1} h[k] \cdot x[n-k]$

Where:
- $y[n]$ is the output signal at time $n$
- $x[n-k]$ is the input signal delayed by $k$ samples
- $h[k]$ are the filter coefficients (impulse response)
- $M$ is the length of the filter (number of coefficients)
