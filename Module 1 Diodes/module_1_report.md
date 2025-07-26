# Module 1: Power Diodes and Rectifiers

## 1. Introduction

Power diodes are semiconductor devices designed to handle high current and voltage levels in power electronic circuits. This report examines the fundamental characteristics of power diodes, their classifications, and their application in rectification circuits. The analysis includes theoretical foundations and practical circuit implementations.

---

## 2. Power Diode Fundamentals

### 2.1. Device Physics

Power diodes operate according to the Shockley diode equation, which describes the exponential relationship between current and voltage:

$$
I_D = I_S \left( e^{\frac{V_D}{n V_T}} - 1 \right)
$$

Where:
- $I_D$: Diode current
- $I_S$: Reverse saturation current
- $V_D$: Diode voltage
- $n$: Ideality factor
- $V_T$: Thermal voltage

Power diodes feature a vertically oriented structure with a lightly doped drift region, enabling high reverse voltage blocking capability.

<!-- Image placeholder -->
<div align="center">
  <img src="./images/diode_structure.png" alt="Power Diode Structure" width="500"/>
  <p><i>Figure 1: Power diode cross-sectional structure</i></p>
</div>

### 2.2. Key Parameters

Critical specifications for power diodes include:
- Maximum repetitive reverse voltage (V_RRM)
- Average forward current (I_F(AV))
- Reverse recovery time (t_rr)
- Forward voltage drop (V_F)
- Thermal resistance (R_th)

---

## 3. Diode Classifications

### 3.1. General-Purpose Diodes
Designed for low-frequency applications (50-400 Hz). Characteristics:
- High current and voltage ratings
- Relatively long reverse recovery time
- Robust construction for harsh environments

### 3.2. Fast-Recovery Diodes
Optimized for high-frequency switching applications. Features:
- Short reverse recovery time (< 500 ns)
- Reduced switching losses
- Applications in DC-DC converters and inverters

### 3.3. Schottky Diodes
Utilize metal-semiconductor junction. Properties:
- Low forward voltage drop (0.3-0.5 V)
- Negligible reverse recovery time
- Limited reverse voltage capability (< 200 V)

---

## 4. Freewheeling Operation

Freewheeling diodes provide a current path for inductive loads when switching elements are turned off. This prevents voltage spikes that could damage circuit components. The energy stored in the inductor (E = ½LI²) is safely dissipated through the freewheeling path.

<!-- Image placeholder -->
<div align="center">
  <img src="./images/freewheeling_circuit.png" alt="Freewheeling Diode Application" width="450"/>
  <p><i>Figure 2: Freewheeling diode in inductive circuit</i></p>
</div>

---

## 5. Rectifier Circuit Analysis

### 5.1. Single-Phase Full-Wave Bridge Rectifier

The bridge configuration uses four diodes to achieve full-wave rectification. Key parameters:

**Average Output Voltage:**
$$V_{dc} = \frac{2V_m}{\pi}$$

**RMS Output Voltage:**
$$V_{rms} = \frac{V_m}{\sqrt{2}}$$

**Ripple Factor:**
$$RF = \sqrt{\left(\frac{V_{rms}}{V_{dc}}\right)^2 - 1} = 0.482$$

### 5.2. Three-Phase Full-Wave Bridge Rectifier

Six-diode configuration for three-phase AC conversion. Performance metrics:

**Average Output Voltage:**
$$V_{dc} = \frac{3\sqrt{3}V_{m,LL}}{2\pi}$$

**Ripple Factor:**
$$RF \approx 0.042$$

<!-- Image placeholder -->
<div align="center">
  <img src="./images/rectifier_comparison.png" alt="Rectifier Output Waveforms" width="600"/>
  <p><i>Figure 3: Single-phase vs. three-phase rectifier output comparison</i></p>
</div>

---

## 6. Performance Analysis

Rectifier performance is evaluated using the following metrics:
- **Efficiency (η):** Ratio of DC output power to AC input power
- **Transformer Utilization Factor (TUF):** Effective use of transformer rating
- **Peak Inverse Voltage (PIV):** Maximum reverse voltage across diodes
- **Form Factor (FF):** Ratio of RMS to average values

---

## 7. Simulation and Results

Circuit simulations validate theoretical analysis and provide insight into practical performance. Simulation files and experimental data should be documented in the appropriate directories.

### File Organization:
- **[Simulation Files](./simulation_files/):** LTSpice circuit files and netlists
- **[Images and Data](./images/):** Circuit diagrams, waveforms, and measurement data

---

## 8. Conclusions

Power diodes serve as fundamental building blocks in power electronic systems. Understanding their characteristics and proper application is essential for efficient circuit design. The choice between diode types depends on specific application requirements including switching frequency, voltage rating, and efficiency considerations.
