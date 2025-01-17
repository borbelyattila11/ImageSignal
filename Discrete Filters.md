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

## IIF (Infinite Impulse Response)
The output depends not only on the current and past input samples but also on past output samples. The impulse response of these filters doesn't settle to zero but continues indefinitely due to the feedback mechanism.

#### Characteristics:
1. **Feedback:** They use feedback, meaning the past outputs are fed back into the filter to influence the current output.
2. **Stability:** Stability depends on the placement of poles in the filter's transfer function. Can become unstable if not properly designed.
3. **Efficiency:** Achieve a desired frequency response using fewer coefficients than FIR filters.
4. **Phase:** Typically do not have linear phase, which can cause phase distortion.

The relationship between the input $x[n]$ and output $y[n]$ of an IIR filter is governed by the following difference equation:

$y[n] = \sum_{k=0}^{M-1} b[k]x[n-k] - \sum_{l=1}^{L-1} a[l]y[n-l]$

Where:
- $y[n]$ is the output signal at time $n$
- $x[n-k]$ is the input signal delayed by $k$ samples
- $b[k]$ feedforward coefficients
- $a[l]$ feedback coefficients
- $M$ is the number of feedforward coefficients
- $L$ is the number of feedback coefficients

## Stable filters in the view of the Transfer function
**Stability** of a filter in terms of its transfer function means that the system's output remains bounded for any bounded input. A discrete-time filter is **stable** if the poles of its transfer function lie within the unit circle in the z-plane (|z| < 1). For an IIR filter, the location of the poles determines the stability, FIR filters are always stable because their transfer functions do not have poles.

## Realizable Filtesr in the view of the Transfer function
A **realizable filter** is a filter that can be implemented using real, physical components. For a filter to be realizable, its transfer function must be **causal** and **stable**. In practice, both FIR and IIR filters are realizable, but IIR filters require careful design to ensure that they meet these conditions.

## Notes:
- **Poles:** Poles are the values of $z$ that makes the denominator $A(z) = 0$, causing the transfer function $H(z)$ to approach infinity. Poles represent the frequencies at which the system's response becomes theoretically infinite.
