# Design Notes

## Project Summary

This project implements a five-transistor CMOS Operational Transconductance Amplifier (OTA) using Cadence Virtuoso (GPDK180). The objective was to follow a structured analog IC design methodology beginning with transistor characterization and ending with performance verification through simulation.

---

# Design Workflow

The OTA was designed using the following sequence:

1. NMOS device characterization.
2. Extraction of ID–VGS characteristics.
3. Extraction of gm–ID relationship.
4. Selection of operating point corresponding to the target transconductance.
5. Transistor sizing.
6. Differential pair bias optimization.
7. Verification of saturation through operating-point analysis.
8. AC frequency response analysis.
9. Temperature characterization.

---

# Device Characterization

Prior to circuit implementation, a single NMOS transistor was characterized over a range of gate voltages.

The following quantities were extracted:

- Drain current (ID)
- Transconductance (gm)
- Threshold voltage (VTH)

The gm–ID characteristic was used to identify the operating current required to achieve the design target of approximately **2 mS** transconductance.

---

# OTA Architecture

The implemented OTA consists of

- NMOS differential input pair
- PMOS current mirror active load
- NMOS tail bias transistor

The output is taken single-ended from one branch of the differential pair.

---

# Design Decisions

## Why characterize the transistor first?

Instead of arbitrarily selecting transistor dimensions, characterization provides quantitative information regarding the relationship between drain current and transconductance.

This enables a more systematic selection of the operating point.

---

## Why use a differential pair?

The differential pair provides

- differential amplification
- improved common-mode rejection
- compatibility with current-mirror active loads
- suitability for operational transconductance amplifiers

---

## Why use active loads?

PMOS current mirrors provide significantly higher small-signal output resistance than resistive loads, resulting in increased voltage gain while occupying less silicon area.

---

## Bias Optimization

Multiple bias voltages were investigated before arriving at the final operating point.

The final bias values were selected based on

- saturation of every transistor
- target transconductance
- stable DC operating point
- acceptable AC performance

---

# Simulation Results

The final implementation achieved

- gm ≈ 2.06 mS
- Open-loop gain ≈ 26.8 dB
- Bandwidth ≈ 295 MHz

All transistors remained in saturation during DC operating-point verification.

---

# Temperature Analysis

The input transistor transconductance was evaluated over the temperature range

-20°C to +100°C.

The observed reduction in transconductance is consistent with the expected decrease in carrier mobility as temperature increases.

---

# Limitations

The current implementation does not include

- constant-gm bias circuit
- process corner analysis
- Monte Carlo mismatch analysis
- layout implementation
- post-layout extraction

These remain potential future improvements.

---

# Future Work

Potential extensions of this project include

- Constant-gm bias generation using negative feedback
- Process-voltage-temperature (PVT) verification
- Monte Carlo mismatch analysis
- Layout implementation
- DRC/LVS verification
- Post-layout simulation
- Noise characterization
- Power optimization

---

# Software

- Cadence Virtuoso
- Spectre Simulator
- GPDK180 Technology Library
