# 2-Stage Operational Transconductance Amplifier (OTA)

A CMOS implementation of a two-stage operational transconductance amplifier designed and simulated in LTSpice.

## Overview

This project implements a classic 2-stage OTA topology using CMOS technology. The design consists of a differential input stage followed by a common-source amplifier stage, providing high gain and good frequency response characteristics.

## Circuit Architecture

### Stage 1: Differential Input Stage
- **Differential Pair**: M1A, M1B (NMOS input transistors)
- **Current Mirror Load**: M2A, M2B (PMOS active load)
- **Tail Current Source**: M0 (NMOS current source)
- **Bias**: Mref (NMOS reference transistor)

### Stage 2: Common Source Amplifier
- **Amplifying Transistor**: M3 (NMOS)
- **Active Load**: M4 (PMOS current source)

### Compensation Network
- **Miller Compensation**: C2 (2.2pF) between stages
- **Load Capacitance**: C1 (10pF)
- **Feedback Resistor**: R1 (20kΩ)

## Key Features

- **Two-stage topology** for high DC gain
- **Miller compensation** for frequency stability
- **CMOS implementation** for low power consumption
- **Differential input** for common-mode rejection
- **Single-ended output** configuration

## Simulation Results

### DC Operating Points
- **Supply Voltage**: 1.8V
- **Input Common Mode**: ~1.017V
- **Output Quiescent**: ~515mV
- **Power Consumption**: Low static power design

### AC Performance
- High open-loop gain
- Controlled frequency response with compensation
- Stable operation under feedback conditions

## Files Structure

```
├── open_loop.asc    # Open-loop configuration
├── closed_loop.asc  # Closed-loop configuration
├── README.md        # This file
├── DC_Plots_Report.pdf    # DC simulation                          
└── AC_Plots_Report.pdf    # AC simulation
```

## Design Specifications

| Parameter | Value | Unit |
|-----------|-------|------|
| Supply Voltage | 1.8 | V |
| Technology | CMOS | 180nm |
| Compensation Capacitor | 2.2 | pF |
| Load Capacitor | 10 | pF |
| Feedback Resistor | 20 | kΩ |

## Usage

### Open Loop Simulation
1. Open `open_loop.asc` in LTSpice
2. Run DC operating point analysis
3. Perform AC analysis for frequency response
4. Analyze gain and phase margins

### Closed Loop Simulation
1. Open `closed_loop.asc` in LTSpice
2. Configure feedback network
3. Run transient analysis for step response
4. Verify stability and settling time

## Key Design Considerations

### Stability
- Miller compensation (C2) ensures phase margin
- Proper sizing of compensation capacitor
- Right-half-plane zero compensation

### Performance Trade-offs
- **Gain vs Bandwidth**: Higher gain reduces bandwidth
- **Power vs Speed**: Lower power consumption affects slew rate
- **Noise vs Power**: Larger transistors reduce noise but increase power

### Biasing
- Proper bias current distribution
- Temperature-independent biasing
- Process variation tolerance

## Simulation Setup

### Required Models
- TSMC 180nm CMOS models (tsmc018.lib)
- AC analysis: 1Hz to 10GHz
- Transient analysis: 10μs simulation time

### Test Conditions
- **Supply**: 1.8V single supply
- **Load**: 10pF capacitive load

## Future Enhancements

- [ ] Add folded-cascode input stage for higher gain
- [ ] Add common-mode feedback (CMFB) circuit
- [ ] Optimize for specific applications (ADC, filter, etc.)


## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- TSMC for the 180nm process models
- LTSpice simulation environment
- Academic institution support

---

*For questions or collaboration, please open an issue or contact me.*
