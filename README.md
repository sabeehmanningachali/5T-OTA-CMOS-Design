# Design and Characterization of a Five-Transistor CMOS OTA

A simulation-driven analog IC design project implementing a five-transistor CMOS Operational Transconductance Amplifier (OTA) using **Cadence Virtuoso** and the **GPDK180** technology library.

---

## Project Overview

The objective of this project was to design and characterize a five-transistor CMOS OTA while following a structured analog IC design methodology instead of relying on trial-and-error transistor sizing.

The design flow consisted of:

- MOSFET characterization
- gm–ID based operating-point selection
- OTA implementation
- Operating-point verification
- AC frequency response analysis
- Temperature characterization

---

## Design Specifications

| Parameter | Value |
|-----------|-------|
| Technology | GPDK180 |
| Supply Voltage | 1.8 V |
| Architecture | Five-Transistor OTA |
| Target Transconductance | 2 mS |
| Design Environment | Cadence Virtuoso ADE L |

---

## Design Methodology

The design followed the workflow below:

1. Characterize an NMOS transistor.
2. Obtain the gm–ID relationship.
3. Determine the operating current corresponding to the target transconductance.
4. Size the OTA transistors.
5. Verify saturation using operating-point analysis.
6. Refine bias conditions.
7. Validate gain, bandwidth and temperature performance.

---

## Simulation Results

| Parameter | Result |
|-----------|--------|
| Input Transconductance | 2.06 mS |
| Voltage Gain | 26.8 dB |
| Bandwidth | 295 MHz |
| Temperature Range | -20°C to 100°C |
| Operating Region | Saturation |

---

## Repository Structure

```text
report/
    Final project report

images/
    Simulation plots and Cadence screenshots

docs/
    Additional design notes
```

---

## Tools Used

- Cadence Virtuoso
- Spectre Simulator
- GPDK180 Technology Library

---

## Future Improvements

- Constant-gm bias circuit
- Process corner analysis
- Monte Carlo mismatch analysis
- Layout implementation
- DRC/LVS verification
- Post-layout simulation

---

## Author

Sabeeh Muhammed MC

Department of Electrical Engineering

Indian Institute of Technology Kanpur
