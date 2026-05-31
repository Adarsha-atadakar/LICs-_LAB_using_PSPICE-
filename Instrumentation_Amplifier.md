# INSTRUMENTATION AMPLIFIER

## Aim

To design and analyze the circuit of an Instrumentation Amplifier for different values of R<sub>G</sub>.

## Simulation Tool

TINA

## Components Required

| Component Name | Value / Model |
|---|---|
| Resistor (Ω) | 1k, 3k, 222.22, 20.2, 10.05, 2 |
| Op-Amp | µA741 |
| DC Voltage (Supply) | V<sub>CC</sub> = ±15 V |
| Voltage Source | Signal: Sinusoidal |

---

## For Gain of 1

### Schematic Circuit

<img width="1122" height="587" alt="image" src="https://github.com/user-attachments/assets/37114d18-5e77-419b-85b6-fbef3dfa3adc" />

### Design

<!-- Insert design calculations here -->

### Simulation Results

#### Transient Analysis

<img width="1122" height="524" alt="image" src="https://github.com/user-attachments/assets/5169e058-1bec-4b48-8f32-41d8b6351174" />


---

## For Gain of 10

### Schematic Circuit

<img width="1122" height="593" alt="image" src="https://github.com/user-attachments/assets/9244063a-f6a9-47ca-9e13-c704fdf913f8" />


### Design

<!-- Insert design calculations here -->

### Simulation Results

#### Transient Analysis

<img width="1122" height="519" alt="image" src="https://github.com/user-attachments/assets/79ee42da-9c3c-4223-ba54-e9a4f61b9ac1" />


---

## For Gain of 100

### Schematic Circuit

<img width="1122" height="552" alt="image" src="https://github.com/user-attachments/assets/93c216ff-a522-447e-bf86-5cb024fca5aa" />


### Design

<!-- Insert design calculations here -->

### Simulation Results

#### Transient Analysis
<img width="1122" height="519" alt="image" src="https://github.com/user-attachments/assets/b394d54e-d83a-456b-b47e-1733609040d4" />


---

## For Gain of 200

### Schematic Circuit

<img width="1122" height="605" alt="image" src="https://github.com/user-attachments/assets/114dded7-c3e9-4497-ac13-d7aab1926cc2" />


### Design

<!-- Insert design calculations here -->

### Simulation Results

#### Transient Analysis

<img width="1122" height="522" alt="image" src="https://github.com/user-attachments/assets/0cabcd24-c6b4-4bff-9ae3-a48519e83b40" />


---

## For Gain of 1000

### Schematic Circuit
<img width="1122" height="607" alt="image" src="https://github.com/user-attachments/assets/8390f78d-24cf-4ac2-9f20-e8d84b994764" />


### Design

<!-- Insert design calculations here -->

### Simulation Results

#### Transient Analysis

<img width="1122" height="521" alt="image" src="https://github.com/user-attachments/assets/d4d8ed59-837c-426f-9942-f89da77de9e9" />

---

## Inference

The instrumentation amplifier was simulated for five gain settings (1, 10, 100, 200, and 1000) by varying R<sub>G</sub>, while keeping all other resistors fixed. The following observations were made:
 
- **Gain vs R<sub>G</sub>:** The simulated output voltage closely matched the theoretical gain expression `A_v = 1 + (2R/R_G)` for all five cases, confirming that gain is accurately and predictably controlled by R<sub>G</sub> alone.
- **CMRR and noise rejection:** The three op-amp topology (two input buffers + one difference amplifier) effectively rejected common-mode signals. Both differential input terminals tracked common-mode variations identically, with only the differential component appearing at the output — demonstrating the high CMRR advantage of this architecture over a single op-amp difference amplifier.
- **Gain accuracy:** At lower gains (1, 10), the output waveform was clean and undistorted. At higher gains (100, 200, 1000), the output amplitude scaled correctly, though the µA741's finite gain-bandwidth product (≈1 MHz) begins to limit phase margin and bandwidth at high gain settings.
- **Op-amp limitations:** The µA741's slew rate (0.5 V/µs) and input offset voltage introduce minor deviations at high gains and high-frequency inputs. These are inherent device limitations and not design errors.

## Conclusion

The instrumentation amplifier circuit was successfully designed and simulated using TINA with the µA741 op-amp for gain values of 1, 10, 100, 200, and 1000. The simulation results closely matched theoretical predictions in all cases, validating the design.
 
The experiment demonstrated that the instrumentation amplifier provides precise, single-resistor gain control, high CMRR, and high input impedance — making it highly suitable for sensor signal conditioning applications such as ECG front-ends, strain gauge bridges, and temperature measurement systems. The µA741's bandwidth and slew rate were identified as the primary limiting factors at high gains, suggesting that a higher-performance op-amp (e.g., INA128 or AD620) would be preferred in a real-world implementation.

---
