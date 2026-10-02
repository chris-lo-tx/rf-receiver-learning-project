# Antenna Fundamentals

## Purpose of an Antenna

An antenna is a transducer between guided electrical RF energy and electromagnetic waves propagating through space.

During transmission:

\[
\text{Electrical RF energy}
\rightarrow
\text{Electromagnetic wave}
\]

During reception:

\[
\text{Electromagnetic wave}
\rightarrow
\text{Electrical RF signal}
\]

This project uses antennas only for reception.

## Receiving an Electromagnetic Wave

An incoming electromagnetic wave contains changing electric and magnetic fields.

When the electric field interacts with a conductive antenna, forces are exerted on charges within the conductor. This produces a small RF voltage and current at the antenna feedpoint.

```text
Incoming EM wave
→ → → → → →

       │
       │
       │
       ● ← Feedpoint
       │
       │
       │
       ↓
     Coax
       ↓
   Receiver
```

The received signal may be extremely small, which makes receiver sensitivity, noise, filtering, and amplification important.

## Frequency and Wavelength

Frequency and wavelength are related by:

\[
\lambda=\frac{c}{f}
\]

where:

- \(\lambda\) = wavelength in meters
- \(c\) = speed of light, approximately \(3\times10^8\text{ m/s}\)
- \(f\) = frequency in Hz

For a 100 MHz signal:

\[
\lambda=
\frac{3\times10^8}
{100\times10^6}
\]

\[
\lambda\approx3\text{ m}
\]

The wavelength is therefore approximately 3 meters.

## Half-Wave Dipole

A common antenna is the half-wave dipole.

Its approximate total length is:

\[
L\approx\frac{\lambda}{2}
\]

At 100 MHz:

\[
L\approx1.5\text{ m}
\]

A dipole consists of two elements, making each approximately:

\[
L_{\text{element}}\approx\frac{\lambda}{4}
\]

or:

\[
L_{\text{element}}\approx0.75\text{ m}
\]

Real antenna dimensions may differ somewhat from the ideal calculation because of conductor geometry, nearby materials, construction, and environmental effects.

## Antenna Impedance

An antenna has an impedance that can be represented as:

\[
Z_A=R_A+jX_A
\]

where:

- \(R_A\) represents the resistive portion
- \(X_A\) represents the reactive portion

Near resonance:

\[
X_A\approx0
\]

and therefore:

\[
Z_A\approx R_A
\]

An ideal thin half-wave dipole in free space has a feedpoint impedance of approximately 73 Ω.

Real antennas may differ considerably depending on their construction and surroundings.

## Polarization

The orientation of the electric field of an electromagnetic wave defines its polarization.

A receiving antenna generally receives the strongest signal when its polarization is appropriately aligned with the transmitted wave.

One Phase 1 experiment will involve rotating the dipole while observing received signal strength on the SDR.

This will allow antenna polarization to be observed experimentally rather than only theoretically.
