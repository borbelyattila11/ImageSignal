# Signals
Signals are typically used to transmit information and can be either continous or discrete. A signal is a function that maps one or more independent variables (time) to a set of dependent variables. $s(t)$ or $s(t, x, y)$

#### Characteristics of Signals
- **Amplitude:** The magnitude of the signal at any point.
- **Frequency:** How often the signal oscillates or repeats within a given time.
- **Phase:** The relative position of the waveform with respect to time.
- **Energy and Power:** Measures of the strength or intensity of the signal.

## Analog Signals
Analog signals are conitnous in both time and amplitude, they can take any value within a given range and are represented as a smooth wave.

Examples:
- Heavyside function
- Rectangle function
- Dirac-delta (unit impulse)
- Sinc
- Sinus (monochormatic)
- Complex Trigonometric

## Discrete Signals
Discrete signals are defined only at specific time intervals, with values at discrete points. They are discrete in time and continous in amplitude.

Examples:
- Unit Impulse Signal (Discrete) $x[n] = 1$ if $n = 0$ else $0$

## Digital Signals
Digital signals are discrete in both time and amplitude, typically represented as binary values (0 and 1).

Examples:
- Data transmitted in computer networks
- Audio files (MP3, WAV)
- Images in digital format

# Systems
A system processes input signals to produce output signals. The space of input signals $(X)$ and the space of output signals $(Y)$ are linear spaces.

1. **Linear Systems:** A system is linear if it satisfies the principles of superposition (additivity and homogeneity)
2. **Time-Invariant Systems:** A system is time-invariant if its behavior and characteristics do not change over time. In simpler terms, shifting or delaying the input to the system results in an equivalent shift or delay in the output.
3. **Realizable Systems:** A system is realizable if it can be physically implemented, must have a causal structure, where the output depends only on the current and past inputs, not future inputs.
4. **Stable Systems:** A system is stable if bounded input signals always produce bounded output signals (BIBO stability).
