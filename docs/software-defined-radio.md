# Software-Defined Radio Fundamentals

## Overview

A Software-Defined Radio (SDR) is a radio system in which many functions traditionally performed by dedicated analog hardware are instead performed digitally using software.

A traditional receiver may contain dedicated hardware for filtering, frequency conversion, demodulation, and audio processing.

A simplified traditional receiver is:

```text
Antenna
   ↓
RF Filter
   ↓
RF Amplifier
   ↓
Mixer / Local Oscillator
   ↓
Intermediate-Frequency Filter
   ↓
Demodulator
   ↓
Audio Amplifier
   ↓
Speaker
```

An SDR moves some of these operations into the digital domain:

```text
Antenna
   ↓
Analog RF Front End
   ↓
ADC
   ↓
Digital I/Q Samples
   ↓
Computer / DSP
   ├── Filtering
   ├── FFT
   ├── Demodulation
   └── Spectrum/Waterfall Display
```

The Analog-to-Digital Converter (ADC) represents an important boundary.

Before the ADC, the system processes physical voltages and currents.

After the ADC, software processes numerical representations of those signals.

## RTL-SDR

The RTL-SDR being used in this project contains an RF tuner and ADC.

The basic signal path is:

```text
Antenna
   ↓
RF Tuner
   ↓
ADC
   ↓
USB
   ↓
Computer
```

The tuner allows a particular portion of the RF spectrum to be selected and converted into a form suitable for digitization.

The resulting samples are sent over USB to the computer, where SDR software performs additional signal processing.

## I/Q Signals

SDRs commonly represent received signals using two components:

- I — In-phase
- Q — Quadrature

The quadrature component is separated from the in-phase component by 90°.

These can be represented mathematically as a complex signal:

\[
x(t)=I(t)+jQ(t)
\]

This representation preserves amplitude and phase information and makes many digital signal-processing operations convenient.

This is conceptually related to the complex-number and phasor representations used in AC circuit analysis.

## Spectrum Display

An SDR spectrum display shows received signal magnitude or power versus frequency.

```text
Power
  ↑
  │                 /\
  │       /\       /  \
  │______/__\_____/____\_______→ Frequency
```

The computer can calculate this representation from sampled time-domain data using a Fast Fourier Transform (FFT).

Conceptually:

\[
\text{Time-domain samples}
\xrightarrow{FFT}
\text{Frequency-domain information}
\]

## Waterfall Display

A waterfall adds time as another dimension.

Each horizontal line represents a spectrum measurement at a particular point in time. New measurements are continuously added.

The result displays:

- Frequency
- Signal strength
- Time

This makes it possible to visually observe transmissions beginning, ending, changing frequency, or changing strength.

## Role of the SDR in This Project

The objective of this project is not to develop SDR software.

The SDR will instead serve as a receive-only RF instrument that allows signals to be observed while external RF hardware is designed and tested.

The eventual system will resemble:

```text
Antenna
   ↓
Matching Network
   ↓
RF Filter
   ↓
Low-Noise Amplifier
   ↓
Additional Filtering
   ↓
RTL-SDR
   ↓
Computer / SDR Software
```

The antenna, matching networks, filters, and amplifiers will progressively become the primary hardware-design portion of the project.
