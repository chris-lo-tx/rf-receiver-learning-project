# Transmission Lines and Impedance Matching

## Overview

As part of Phase 1 of my receive-only RF project, I began studying how RF signals travel between an antenna and a receiver.

At lower frequencies, wires can often be approximated as ideal connections between circuit nodes. At RF frequencies, the physical length and construction of a conductor become important because voltage and current propagate along the conductor as waves.

This introduces several important concepts:

- Transmission lines
- Characteristic impedance
- Impedance matching
- Signal reflections
- Reflection coefficient
- Standing waves
- VSWR

These concepts help explain why RF systems commonly use controlled impedances such as 50 ohms.

---

## 1. From Wires to Transmission Lines

In introductory circuit analysis, a wire is often approximated as having the same voltage everywhere along it.

For example:

Source -------- Wire -------- Load

At sufficiently high frequencies, this approximation becomes less accurate.

An electromagnetic signal takes time to propagate through a cable. When the cable length becomes significant compared with the wavelength of the signal, the cable must be treated as a **transmission line**.

The wavelength of an electromagnetic wave in free space is:

\[
\lambda = \frac{c}{f}
\]

where:

- lambda = wavelength
- c = speed of light
- f = frequency

At approximately 100 MHz:

\[
\lambda \approx 3\text{ m}
\]

Therefore, cable lengths encountered in an RF system can represent a significant fraction of a wavelength.

Instead of thinking only in terms of node voltages, it becomes useful to think about waves traveling along the cable:

Source -------- Incident Wave --------> Load

If the system is mismatched, another wave can travel back toward the source:

Source <------- Reflected Wave -------- Load

---

## 2. Distributed Circuit Model

A transmission line contains electrical properties distributed throughout its physical length.

These include:

- Resistance per unit length
- Inductance per unit length
- Capacitance per unit length
- Conductance per unit length

A simplified model can be represented as repeated small sections containing inductance and capacitance.

This is different from treating the cable as one lumped component.

For an ideal lossless transmission line, its characteristic impedance is:

\[
Z_0 = \sqrt{\frac{L'}{C'}}
\]

where:

- \(L'\) = inductance per unit length
- \(C'\) = capacitance per unit length

---

## 3. Characteristic Impedance

The coaxial cable used in this project is designed around a characteristic impedance of approximately:

\[
Z_0 = 50\Omega
\]

This does **not** mean the cable contains a 50-ohm resistor.

Characteristic impedance describes the relationship between voltage and current for a traveling wave on the transmission line:

\[
Z_0 = \frac{V^+}{I^+}
\]

For a 50-ohm transmission line, an incident wave with a voltage amplitude of 1 V would have an associated current amplitude of:

\[
I^+ = \frac{1}{50}
\]

\[
I^+ = 20\text{ mA}
\]

Therefore:

\[
\frac{V^+}{I^+} = 50\Omega
\]

---

## 4. Impedance Matching

Ideally, the load connected to a transmission line has an impedance equal to the characteristic impedance of the line.

For example:

\[
Z_0 = 50\Omega
\]

and:

\[
Z_L = 50\Omega
\]

This is called a **matched system**.

A simplified RF signal chain might therefore be:

Antenna -> 50-ohm Coax -> 50-ohm Filter -> 50-ohm Receiver

When the load is matched to the transmission line, the incident wave can satisfy the required voltage/current relationship at the load without producing a reflected wave.

---

## 5. Impedance Mismatch and Reflections

Suppose a 50-ohm transmission line is connected to a 100-ohm load.

The traveling wave has the relationship:

\[
\frac{V^+}{I^+} = 50\Omega
\]

but the load requires:

\[
\frac{V_L}{I_L} = 100\Omega
\]

The incident wave by itself cannot satisfy both conditions at the load boundary.

A reflected wave is therefore produced.

The total voltage at the load is the combination of the incident and reflected voltage waves:

\[
V_L = V^+ + V^-
\]

The currents combine with the appropriate direction convention:

\[
I_L = I^+ - I^-
\]

Together, the incident and reflected waves establish the voltage/current ratio required by the load impedance.

---

## 6. Reflection Coefficient

The reflection coefficient describes the amplitude and phase of the reflected voltage wave relative to the incident voltage wave.

It is represented by:

\[
\Gamma = \frac{Z_L-Z_0}{Z_L+Z_0}
\]

For a 50-ohm transmission line connected to a 100-ohm resistive load:

\[
\Gamma =
\frac{100-50}{100+50}
\]

\[
\Gamma = 0.333
\]

Therefore, the reflected voltage-wave amplitude is approximately 33.3% of the incident voltage-wave amplitude.

The fraction of incident power reflected is:

\[
\frac{P_R}{P_I}=|\Gamma|^2
\]

Therefore:

\[
(0.333)^2 \approx 0.111
\]

or approximately:

\[
11.1\%
\]

of the incident power.

A perfectly matched system has:

\[
\Gamma = 0
\]

meaning there is ideally no reflected wave.

---

## 7. Complex Loads and Phase

RF loads do not have to be purely resistive.

An antenna impedance can be represented as:

\[
Z_A = R + jX
\]

where:

- \(R\) is resistance
- \(X\) is reactance

Because the load can be complex, the reflection coefficient can also be complex:

\[
\Gamma = |\Gamma|\angle\theta
\]

The magnitude describes the size of the reflected wave, while the angle describes its phase relative to the incident wave.

This connects RF transmission-line analysis to the complex impedance and phasor concepts used in AC circuit analysis.

---

## 8. Standing Waves

When both an incident and reflected wave exist on a transmission line, they combine through constructive and destructive interference.

At some physical locations along the transmission line, their voltages reinforce each other.

At other locations, they partially cancel.

This creates locations of maximum and minimum voltage:

\[
V_{max}
\]

and:

\[
V_{min}
\]

The resulting spatial pattern is called a **standing wave**.

Standing waves therefore provide physical evidence that reflections are occurring on a transmission line.

---

## 9. Voltage Standing Wave Ratio (VSWR)

VSWR describes the ratio between the maximum and minimum voltage magnitudes of the standing-wave pattern.

\[
VSWR=\frac{V_{max}}{V_{min}}
\]

It can also be calculated from the magnitude of the reflection coefficient:

\[
VSWR=
\frac{1+|\Gamma|}
{1-|\Gamma|}
\]

A perfectly matched transmission line has:

\[
\Gamma=0
\]

and therefore:

\[
VSWR=1
\]

which is written as:

\[
1:1
\]

For the previous example where:

\[
|\Gamma|=0.333
\]

the VSWR is approximately:

\[
VSWR=
\frac{1+0.333}
{1-0.333}
\approx2
\]

giving:

\[
2:1
\]

A VSWR closer to 1:1 indicates a better impedance match.

---

## 10. Application to the Dipole Experiment

An ideal thin half-wave dipole in free space has a feedpoint impedance of approximately:

\[
73\Omega
\]

The receiver system in this project uses approximately:

\[
50\Omega
\]

Assuming a purely resistive 73-ohm antenna for a simplified example:

\[
\Gamma=
\frac{73-50}
{73+50}
\]

\[
\Gamma\approx0.187
\]

The corresponding reflected power fraction is:

\[
|\Gamma|^2\approx0.035
\]

or approximately 3.5%.

The VSWR is:

\[
VSWR=
\frac{1+0.187}
{1-0.187}
\approx1.46
\]

giving approximately:

\[
1.46:1
\]

This represents a relatively modest mismatch.

The actual impedance of the antenna used in this project will depend on frequency, element length, construction, feed arrangement, nearby objects, and the surrounding environment.

---

## 11. Impedance Matching Networks

If an antenna or circuit does not have the desired impedance, reactive components can be used to transform the impedance presented to another part of the system.

For example:

Antenna -> Matching Network -> 50-ohm Coax -> Receiver

Matching networks can be constructed using inductors and capacitors.

Their impedances are frequency dependent:

\[
Z_L=j\omega L
\]

and:

\[
Z_C=\frac{1}{j\omega C}
\]

This means a matching network can be designed to provide a desired impedance transformation around a particular operating frequency.

This connects RF impedance matching directly to AC circuit analysis.

---

## 12. Measuring the System

The RTL-SDR can show how strongly a signal is being received, but received signal strength alone does not directly measure antenna impedance or impedance matching.

A Vector Network Analyzer (VNA) can directly characterize RF networks.

For an antenna, a VNA can measure quantities such as:

- S11
- Reflection coefficient
- Return loss
- VSWR
- Complex impedance
- Resonant behavior versus frequency

This will eventually allow the antenna-length experiment to be repeated using direct impedance measurements rather than relying only on received signal strength.

---

## Key Lessons Learned

1. At RF frequencies, cables may need to be treated as transmission lines rather than ideal wires.

2. A 50-ohm coaxial cable does not contain a 50-ohm resistor. The value describes its characteristic impedance.

3. A traveling wave has a voltage/current relationship determined by the characteristic impedance of the transmission line.

4. When the load impedance differs from the transmission-line impedance, part of the wave is reflected.

5. Reflection coefficient describes the amplitude and phase relationship between the reflected and incident voltage waves.

6. Incident and reflected waves can combine to create standing waves along the transmission line.

7. VSWR provides a convenient measure of impedance mismatch.

8. RF systems commonly use standardized impedances, such as 50 ohms, to make components easier to connect predictably.

9. Inductors and capacitors can be used to construct impedance-matching networks because their impedances vary with frequency.

10. An SDR is useful for observing received signals, while a VNA provides much more direct information about antenna and RF-network impedance behavior.

## Connection to This Project

The current receive chain is:

Dipole Antenna -> 50-ohm Coax -> RTL-SDR

Understanding transmission lines and impedance matching establishes the theory needed for the next stages of the project:

- Measuring antenna impedance
- Understanding S11 and return loss
- Using a NanoVNA
- Designing matching networks
- Designing RF filters
- Measuring filter S-parameters
- Eventually integrating an LNA and complete RF front end
