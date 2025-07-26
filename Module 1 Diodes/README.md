# Module 1: Power Diodes Fundamentals

## Temáticas de consulta para el informe:
- Características de los diodos de potencia
- Tipos de diodos (propósito general, recuperación rápida y Schottky)
- Freewheeling
- Rectificadores con diodos: monofásicos (onda completa) y trifásicos
- Parámetros de desempeño
- Diseño de un circuito rectificador

Simulaciones: rectificadores monofásicos y trifásicos


## Objectives
- Understand the characteristics of power diodes
- Identify types of diodes: general purpose, fast recovery, and Schottky
- Analyze freewheeling and rectifier circuits (single-phase and three-phase)
- Evaluate performance parameters
- Design a rectifier circuit

## Activities
- Theoretical research
- Circuit design
- LTSpice simulations: single-phase and three-phase rectifiers

## Report guidelines
- Introduction
- Theoretical background
- Circuit design and simulation
- Results and analysis
- Conclusions

## Tools
- LTSpice
- Markdown
- Python

---

### Team
- David Lujan (david.lujan@upb.edu.co)
- Wilmer Jimenez (wilmer.jimenez@upb.edu.co)
- Joiner Arrieta (joiner.arrieta@upb.edu.co)

### Professor
- MSc Eng. Miguel Ortiz (miguel.ortizp@upb.edu.co)

---

# Report – Module 1: Power Diodes Fundamentals

## Introduction
Power diodes are essential components in modern electronic circuits, especially in power conversion and control applications. Their ability to handle high voltages and currents makes them indispensable in rectification, freewheeling, and protection circuits. This report explores the main characteristics, types, and applications of power diodes, as well as the design and simulation of rectifier circuits using LTSpice.

## Theoretical Background
### Power Diode Characteristics
Power diodes are designed to withstand high current and voltage stresses. Key parameters include:
- Maximum repetitive reverse voltage (V_RRM)
- Average forward current (I_F(AV))
- Surge current capability
- Reverse recovery time

### Types of Power Diodes
- **General Purpose Diodes:** Used in low-frequency applications, robust and reliable.
- **Fast Recovery Diodes:** Optimized for high-frequency switching, with reduced reverse recovery time.
- **Schottky Diodes:** Feature low forward voltage drop and very fast switching, ideal for high-efficiency circuits.

### Freewheeling
Freewheeling diodes provide a path for inductive current when the main switch is off, protecting components and improving efficiency in power converters.

### Rectifiers with Diodes
- **Single-phase full-wave rectifiers:** Convert AC to DC using two or four diodes, commonly used in power supplies.
- **Three-phase rectifiers:** Used in industrial applications for higher power and smoother DC output.

### Performance Parameters
- Output voltage and current
- Ripple factor
- Efficiency
- Peak inverse voltage

## Circuit Design
A single-phase full-wave rectifier was designed using four general-purpose diodes. The circuit was simulated in LTSpice to analyze voltage and current waveforms. Key design considerations included diode ratings, transformer selection, and load resistance.

## Simulation Results
Simulations in LTSpice confirmed the expected behavior:
- The output voltage waveform is pulsating DC with reduced ripple compared to half-wave rectification.
- Current through each diode matches theoretical predictions.
- Freewheeling action was observed in inductive load scenarios.

## Conclusions
Power diodes are fundamental for efficient energy conversion in electronic systems. Understanding their characteristics and correct application is crucial for designing robust power circuits. Simulations validate theoretical concepts and support practical design decisions.
