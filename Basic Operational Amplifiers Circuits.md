# Experiment 05: Basic Operational Amplifier Circuits

**Course:** LIC BEC456B  
**Institution:** The National Institute of Engineering, Mysuru  
**Tool Used:** LTspice  
**Op-Amp Used:** uA741  

---

## Aim

To design and analyze various operational amplifier circuits:

1. Zero Crossing Detector (ZCD)  
2. Comparator  
3. Inverting Amplifier  
4. Non-Inverting Amplifier  
5. Voltage Follower  

---

## Components Used

| Component | Specification |
|----------|--------------|
| Op-Amp | uA741 |
| Resistors | 1kΩ, 10kΩ (typical) |
| Power Supply | ±15 V |
| Input Signal | Sinusoidal |
| Simulation Tool | LTspice |

---

## Theory

According to the lab sheet :contentReference[oaicite:0]{index=0}, the uA741 op-amp consists of:

- Two input terminals:
  - Inverting input (−)
  - Non-inverting input (+)
- One output terminal

The op-amp amplifies the **difference between the two input voltages**.

---

# A) Zero Crossing Detector (ZCD)

## Principle

A Zero Crossing Detector compares the input signal with **0V reference**.

- If input > 0 → Output = +Vsat  
- If input < 0 → Output = −Vsat  

---

## Types

1. Inverting ZCD  
2. Non-Inverting ZCD  

---

## Circuit Description

- Reference voltage = 0V  
- Input = sinusoidal signal  
- No feedback → operates in **open-loop (comparator mode)**  

---

## Input

\[
V_{in} = 5\sin(2000\pi t)
\]

---

## Output Behavior

| Condition | Output |
|----------|--------|
| Vin > 0 | +13 V |
| Vin < 0 | −13 V |

---

## Observation

- Output is a **square wave**
- Switching occurs at **zero crossings**
- Duty cycle = **50%**

---

## Inference

- ZCD converts analog sine wave into digital signal  
- Useful in frequency measurement and waveform shaping  

---

# B) Comparator

## Principle

A comparator compares input voltage with a **reference voltage (Vref ≠ 0)**.

---

## Case Study

### Given:
- \( V_{ref} = -2.5V \)  
- \( V_{in} = 5\sin(2000\pi t) \)

---

## Operation (Non-Inverting Comparator)

| Condition | Output |
|----------|--------|
| Vin > -2.5V | +13 V |
| Vin < -2.5V | −13 V |

---

## Observations

- Output is a **square wave**
- Duty cycle is **not 50%**
- Output stays HIGH most of the time

---

## Inference

- Comparator acts as a **level detector**
- Threshold shifts waveform switching point  

---

# C) Inverting Amplifier

## Circuit Description

- Input applied to **inverting terminal**
- Non-inverting terminal grounded  

---

## Gain Formula

\[
A_v = \frac{V_{out}}{V_{in}} = -\frac{R_f}{R_1}
\]

---

## Observations

- Output is **180° out of phase**
- Gain depends on resistor ratio  

---

## Inference

- Provides signal inversion  
- Widely used in signal processing  

---

# D) Non-Inverting Amplifier

## Circuit Description

- Input applied to **non-inverting terminal**
- Feedback network used  

---

## Gain Formula

\[
A_v = 1 + \frac{R_f}{R_1}
\]

---

## Observations

- Output is **in phase** with input  
- Gain is always **≥ 1**  

---

## Inference

- Used where signal amplification without inversion is required  

---

# E) Voltage Follower (Buffer)

## Principle

- Special case of non-inverting amplifier  
- Gain = 1  

\[
A_v = 1
\]

---

## Observations

- Output follows input exactly  
- No phase shift  

---

## Inference

- Used for **impedance matching**
- Prevents loading effect  

---

# Simulation Details

## Input Signal

\[
V_{in} = 5\sin(2000\pi t)
\]

- Frequency = 1 kHz  
- Amplitude = 5 V  

---

## Supply Voltages

- \( V_{CC} = +15V \)  
- \( V_{EE} = -15V \)  

---

## Practical Observation

- Output saturation observed at:
  \[
  \approx \pm 13V
  \]

---

## Reason

- uA741 is **not rail-to-rail**
- Internal voltage drops limit output swing  

---

# Results

### 1. ZCD Output
- Square wave  
- 50% duty cycle  

### 2. Comparator Output
- Asymmetric square wave  
- Duty cycle depends on Vref  

### 3. Inverting Amplifier
- Output inverted  

### 4. Non-Inverting Amplifier
- Output in phase  

### 5. Voltage Follower
- Output = Input  

---

# Observations Table

| Circuit | Key Feature | Output |
|--------|------------|--------|
| ZCD | Zero reference | Square wave |
| Comparator | Threshold detection | Shifted square wave |
| Inverting Amp | Phase inversion | Amplified inverted signal |
| Non-Inverting Amp | No inversion | Amplified signal |
| Voltage Follower | Unity gain | Same as input |

---

# Overall Inferences

1. Op-amp works as comparator in open-loop mode  
2. ZCD detects zero crossings accurately  
3. Comparator shifts switching threshold  
4. Amplifiers provide controlled gain  
5. uA741 shows non-ideal behavior (±13V saturation)  
6. Slew rate affects output transitions  

---

# Conclusion

The experiment successfully demonstrated the operation of various op-amp configurations using the uA741 IC.

- Zero Crossing Detector and Comparator verified switching behavior  
- Inverting and Non-Inverting amplifiers demonstrated gain and phase properties  
- Voltage follower confirmed unity gain buffering  

The results align with theoretical expectations and highlight practical limitations such as **non-rail-to-rail output and slew rate effects**.

---
