# Module 1: Power Diodes and Rectifiers

## 1. Introduction

Power diodes are semiconductor devices designed for high current and voltage applications in power electronic circuits. This report examines diode characteristics, types, and rectification applications based on established literature [1][2][3].

---

## 2. Power Diode Characteristics

Power diodes operate according to the Shockley equation [1]:

$$I_D = I_S \left( e^{\frac{V_D}{n V_T}} - 1 \right)$$

**Critical Parameters:**
- Maximum reverse voltage (V_RRM): 50V to 6kV
- Average forward current (I_F(AV)): 1A to several kA
- Reverse recovery time (t_rr): 25ns to 30μs
- Forward voltage drop (V_F): 0.7V to 1.5V

<!-- Image placeholder -->
<div align="center">
  <img src="./images/power_diode_structure.png" alt="Power Diode Structure" width="500"/>
  <p><i>Figure 1: Power diode structure</i></p>
</div>

---

## 3. Types of Diodes

**General-Purpose Diodes [1]:**
- Low-frequency applications (50-400 Hz)
- High current/voltage ratings: 1A-4000A, 50V-6000V
- Slow recovery: 25μs-30μs

**Fast-Recovery Diodes [2]:**
- High-frequency switching applications
- Fast recovery: 25ns-500ns
- Used in DC-DC converters, inverters

**Schottky Diodes [3]:**
- Metal-semiconductor junction
- Low V_F: 0.3V-0.5V, negligible t_rr
- Limited to <200V applications

<!-- Image placeholder -->
<div align="center">
  <img src="./images/diode_types_comparison.png" alt="Diode Types" width="500"/>
  <p><i>Figure 2: Diode types comparison</i></p>
</div>

---

## 4. Freewheeling Operation

Freewheeling diodes provide current continuity in inductive circuits when switches open, preventing voltage spikes [1].

**Operation Principle:**
- Inductor energy: $E_L = \frac{1}{2}LI^2$
- Current decay: $i_L(t) = I_0 e^{-\frac{R}{L}t}$
- Voltage limited to diode drop (~1V)

<!-- Image placeholder -->
<div align="center">
  <img src="./images/freewheeling_circuit.png" alt="Freewheeling Circuit" width="400"/>
  <p><i>Figure 3: Freewheeling diode operation</i></p>
</div>

---

## 5. Rectifiers with Diodes

### 5.1. Single-Phase Full-Wave Bridge

Four-diode bridge configuration for AC to DC conversion [2]:

**Key Parameters:**
- Average voltage: $V_{dc} = \frac{2V_m}{\pi} = 0.637 V_m$
- Ripple factor: $RF = 0.482$
- PIV per diode: $PIV = V_m$

### 5.2. Three-Phase Full-Wave Bridge

Six-diode configuration with superior performance [3]:

**Key Parameters:**
- Average voltage: $V_{dc} = \frac{3\sqrt{6}V_{LL}}{\pi} = 1.35 V_{LL}$
- Ripple factor: $RF = 0.042$
- PIV per diode: $PIV = \sqrt{3}V_{LL}$

<!-- Image placeholder -->
<div align="center">
  <img src="./images/rectifier_circuits.png" alt="Rectifier Circuits" width="600"/>
  <p><i>Figure 4: Single-phase and three-phase rectifier circuits</i></p>
</div>

---

## 6. Performance Parameters

**Key Metrics [1][2]:**
- Efficiency: $\eta = \frac{P_{dc}}{P_{ac}}$
- Transformer Utilization Factor: $TUF = \frac{P_{dc}}{VA_{rating}}$
- Total Harmonic Distortion: $THD = \frac{\sqrt{\sum_{n=2}^{\infty} I_n^2}}{I_1}$

**Comparison:**
| Parameter | Single-Phase | Three-Phase |
|-----------|--------------|-------------|
| Ripple Factor | 0.482 | 0.042 |
| Efficiency | ~81% | ~95% |
| TUF | 0.812 | 0.955 |

---

## 7. Rectifier Circuit Design

**Design Steps [1][3]:**
1. Determine load requirements (V_dc, I_dc)
2. Select topology (single-phase vs three-phase)
3. Choose diodes with safety margins
4. Design filter components

**Component Selection:**
- Diode voltage rating: $V_{RRM} \geq 2 \times PIV$
- Diode current rating: $I_{F(AV)} \geq 1.5 \times I_{load}$
- Filter capacitor: $C = \frac{I_{load}}{2fV_{ripple}}$

**Design Example:**
Output: 24V DC, 5A; Input: 230V AC
- PIV = 37.7V → Select 100V diodes
- Average current = 5A → Select 10A diodes
- Filter: C = 22mF for 5% ripple

<!-- Image placeholder -->
<div align="center">
  <img src="./images/rectifier_design.png" alt="Rectifier Design" width="500"/>
  <p><i>Figure 5: Rectifier design methodology</i></p>
</div>

---

## 8. RLC Circuit Behavior with Diodes

RLC circuits with diodes exhibit nonlinear behavior due to diode switching [1]:

**Operating Modes:**
- **Diode ON:** Standard RLC response with $\omega_n = \frac{1}{\sqrt{LC}}$
- **Diode OFF:** Current = 0, capacitor voltage constant

**Applications:** Resonant converters, energy transfer circuits

<!-- Image placeholder -->
<div align="center">
  <img src="./images/rlc_diode_circuit.png" alt="RLC with Diode" width="500"/>
  <p><i>Figure 6: RLC circuit with diode</i></p>
</div>

---

## 9. Simulations

**Objectives:** Validate theory, analyze harmonics, evaluate performance

**Parameters:**
- Single-phase: 230V RMS, 50Hz, 10Ω load
- Three-phase: 400V LL RMS, 50Hz, 5Ω load

**File Organization:**
- **[Simulation Files](./simulation_files/):** LTSpice files (.asc)
- **[Images](./images/):** Waveforms and analysis plots

---

## 10. Conclusions

Power diodes are essential components in power electronics with distinct characteristics for different applications:

- **Diode Selection:** General-purpose for low-frequency, fast-recovery for switching, Schottky for high-efficiency applications
- **Rectifier Performance:** Three-phase systems offer superior performance (4.2% vs 48.2% ripple)
- **Design Considerations:** Safety margins and thermal management are critical
- **Future Trends:** SiC and GaN technologies enable higher frequency and efficiency

---

## References

[1] Erickson, R. W., & Maksimović, D. (2001). *Fundamentals of Power Electronics* (2nd ed.). Springer.

[2] Mohan, N., Undeland, T. M., & Robbins, W. P. (2003). *Power Electronics: Converters, Applications, and Design* (3rd ed.). Wiley.

[3] Rashid, M. H. (2017). *Power Electronics: Devices, Circuits, and Applications* (4th ed.). Pearson.
