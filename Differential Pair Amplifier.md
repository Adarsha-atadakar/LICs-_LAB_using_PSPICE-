# Experiment: Differential Pair Amplifier


**Simulation Tool:** LTspice  
**Technology:** TSMC 180nm CMOS  

---

# Aim

To design and simulate Differential Amplifier Circuits.

---

# Components Required

| Component Name     | Value / Model                                          |
|--------------------|--------------------------------------------------------|
| Resistor           | 2.835 KΩ                                               |
| NMOS & PMOS        | W = as per circuit requirement, L = 360 nm             |
| DC Voltage (Supply)| 1.8 V                                                  |
| Voltage Source     | Signal: Sinusoidal, Amplitude: 1 V, Frequency: 1 kHz, AC amplitude = 1 V |

---

# Design

<img width="618" height="1087" alt="image" src="https://github.com/user-attachments/assets/f69251bc-4da3-43d5-b00f-60d891fdd4e5" />


![Design Page 2](media/image2.jpeg)

![Design Page 3](media/image3.jpeg)

![Design Page 4](media/image4.jpeg)

![Design Page 5](media/image5.jpeg)

---

# Circuit 1

## Schematic Circuit

![Circuit 1 Schematic](media/image6.png)

---

## Simulation Results

### A) DC Analysis

#### DC Operating Point

![DC Operating Point - Circuit 1](media/image7.png)

![DC Operating Point Result - Circuit 1](media/image8.png)

#### DC Sweep

![DC Sweep Setup - Circuit 1](media/image7.png)

![DC Sweep Result - Circuit 1](media/image9.png)

---

### B) Transient Analysis

![Transient Analysis Setup - Circuit 1](media/image10.png)

![Transient Analysis Result - Circuit 1](media/image11.png)

---

### C) AC Analysis

![AC Analysis Setup - Circuit 1](media/image10.png)

![AC Analysis Result - Circuit 1](media/image12.png)

---

# Circuit 2

## Schematic Circuit

![Circuit 2 Schematic](media/image13.png)

---

## Simulation Results

### A) DC Analysis

#### DC Operating Point

![DC Operating Point Setup - Circuit 2](media/image13.png)

![DC Operating Point Result - Circuit 2](media/image14.png)

#### DC Sweep

![DC Sweep Setup - Circuit 2](media/image13.png)

![DC Sweep Result - Circuit 2](media/image15.png)

---

### B) Transient Analysis

![Transient Analysis Setup - Circuit 2](media/image16.png)

![Transient Analysis Result - Circuit 2](media/image17.png)

---

### C) AC Analysis

![AC Analysis Setup - Circuit 2](media/image16.png)

![AC Analysis Result - Circuit 2](media/image18.png)

---

# Circuit 3

## Schematic Circuit

![Circuit 3 Schematic](media/image19.png)

---

## Simulation Results

### A) DC Analysis

#### DC Operating Point

![DC Operating Point Setup - Circuit 3](media/image20.png)

![DC Operating Point Result - Circuit 3](media/image21.png)

#### DC Sweep

![DC Sweep Setup - Circuit 3](media/image20.png)

![DC Sweep Result - Circuit 3](media/image22.png)

---

### B) Transient Analysis

![Transient Analysis Setup - Circuit 3](media/image19.png)

![Transient Analysis Result - Circuit 3](media/image23.png)

---

### C) AC Analysis

![AC Analysis Setup - Circuit 3](media/image19.png)

![AC Analysis Result - Circuit 3](media/image24.png)

---

# Inference

- Gain increases from resistive load → current source → active load.
- Current source improves CMRR and bias stability.
- Active load gives highest gain and better output swing.
- Performance improves with complexity, but matching becomes critical.

---

# Conclusion

MOSFET Differential Pair Amplifier has been designed and the effect of using Drain Resistors, current source at the tail end, and replacing Drain Resistors with PMOSFET and replacing the current source with another NMOSFET are analyzed by DC, Transient, and AC analysis.

---

**Verified by:**

**Date:**
