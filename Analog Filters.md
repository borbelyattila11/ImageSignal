# Analog Filters
Systems that manipulate continous-time signals in the analog domain. They can be categorized based on the frequency response characteristics and are primarly used to allow or suppress specific frequency ranges of signals.

## The Ideal Filter
An ideal filter is theoretical concept that completly passes signals within a certain frequency range (passband) and completely blocks signals outside of this range (stopband). However, ideal filters do not exist in practice, as they would require infinite bandwidth and non-causal behavior.

- **Low-Pass Filters** that allow frequencies below a certain cutoff to pass while attenuating higher frequencies.
- **High-Pass Filters** that allow higher frequencies to pass while attenuating lower frequencies.
- **Band-Pass Filters** that allow a certain band of frequencies to pass.
- **Band-Stop Filters** that attenuate a specific band of frequencies.

## The RC Filter
A Resistor-Capacitor (RC) filter is one of the simplest analog filter, it uses a resistor and capacitor in combination to filter signals. It can function as a low-pass or high-pass filter depending on the configurtion:
- **Low-Pass RC Filter:** Allows low-frequency signals to pass and attenuates high-frequency signals.
- **High-Pass RC Filter:** Allows high-frequency signals to pass and attenuates low-frequency signals.

## The Transfer Function
The transfer function of a filter defines the relationship between the output and input signals in the frequency domain. Usually expressed as a ratio of polynomials.

## Stable Filters in view of the Transfer Function
For a filter to be stable, the poles of its transfer function must lie in the left half of the complex $s$-plane. This means the system's impulse response must decay to zero over time.

## Realizable Filters in view of the Transfer Function
A realizable filter is one whose transfer function corresponds to a physical, causal system and all of their poles and zeros inside the unit circle in the complex plane.

## Notes:
- **Poles:** The poles of a system correspond to the roots of the denominator in the transfer function $H(s)$.
  $H(s) = \frac{N(s)}{D(s)}$
  Where $N(s)$ is the numerator polynomial and $D(s)$ is the denominator polynomial
