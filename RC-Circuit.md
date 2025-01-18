# RC Circuit
An RC Circuit (Resistor-Capacitor circuit) is an analog circuit consisting of a resistor (R) and a capacitor (C).

**Equation:** $Ri(t) + v(t) = x(t)$
- $R$ is the resistor (in ohms, Ω)
- $i(t)$ is the electric current in the circuit (in amperes, A)
- $v(t)$ is the output voltage (in volts, V)
- $x(t)$ is the input voltage (in volts, V)

1. **Low-Pass RC Circuit:** Allows low-frequency signals to pass through attenuating higher frequencies.
   - Transfer Function:
     $H(s) = \frac{1}{1 + sRC}$
2. **High-Pass RC Circuit:** Allows high-frequency signals to pass through while attenuating lower frequencies.
   - Transfer Function:
     $H(s) = \frac{sRC}{1 + sRC}$
3. **Cutoff Frequency:** The frequency at which the signal's power drops to half of its passband value.
   - Defined as:
     $f_c = \frac{1}{2πRC}$

The RC Circuit acts as an analog filter that modifies the amplitude and phase of input signals based on their frequency. It performs continous-time signal filtering.

THe difference equation bridges the gap between analog filtering (RC Circuits) and digital signal processing by providing a mathematical structure that models the behavior of discrete-time systems.
