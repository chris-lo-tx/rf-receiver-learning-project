# Coaxial Cable and Transmission-Line Fundamentals

## Coaxial Cable

Coaxial cable provides a controlled path for RF energy between components.

Its major parts are:

```text
        Outer Jacket
     ┌─────────────────┐
     │     Shield      │
     │  ┌───────────┐  │
     │  │Dielectric │  │
     │  │     ●     │  │
     │  │   Center  │  │
     │  │ Conductor │  │
     │  └───────────┘  │
     └─────────────────┘
```

The center conductor carries the signal.

The dielectric electrically separates the center and outer conductors.

The outer conductor or shield provides the return path and electromagnetic shielding.

The jacket provides mechanical and environmental protection.

## Why RF Cables Are Transmission Lines

In introductory circuit analysis, wires are often approximated as ideal conductors.

At sufficiently high frequencies, this approximation becomes inadequate.

A cable contains distributed electrical properties along its entire length:

- Resistance
- Inductance
- Capacitance
- Conductance

A simplified model is:

```text
      L        L        L
───^^^^─────^^^^─────^^^^──
   |         |         |
   C         C         C
   |         |         |
───────────────────────────
```

Instead of treating the entire cable as one lumped component, its electrical properties are considered distributed throughout its length.

## Characteristic Impedance

A transmission line has a characteristic impedance \(Z_0\).

For an ideal lossless transmission line:

\[
Z_0=\sqrt{\frac{L'}{C'}}
\]

where:

- \(L'\) = inductance per unit length
- \(C'\) = capacitance per unit length

A 50 Ω coaxial cable does **not** contain a 50 Ω resistor.

Instead, 50 Ω describes the voltage-to-current relationship of a traveling wave on that transmission line.

## Common System Impedances

Two common RF system impedances are:

### 50 Ω

Commonly used for:

- RF communications
- SDR equipment
- Laboratory RF equipment
- RF amplifiers
- Antenna systems

### 75 Ω

Commonly used for:

- Cable television
- Television antennas
- Video distribution
- Satellite television systems

This project will primarily use a 50 Ω RF system.

## Common Coax Types

Examples include:

### RG-58

A traditional 50 Ω general-purpose coaxial cable.

### RG-174

A small and flexible 50 Ω coax frequently used for short connections.

### RG-316

A small, flexible 50 Ω coax that is convenient for RF bench jumper cables.

Different cables have different attenuation, flexibility, power handling, shielding, and frequency characteristics.

Cable loss generally increases with frequency.

## Cable Materials

Coaxial cables may use center conductors made from materials such as copper or copper-clad steel.

Dielectrics may use materials such as polyethylene or PTFE.

Material and geometry affect:

- Characteristic impedance
- Signal attenuation
- Velocity of propagation
- Temperature performance
- Flexibility
- Power handling

These properties become increasingly important as operating frequency and cable length increase.
