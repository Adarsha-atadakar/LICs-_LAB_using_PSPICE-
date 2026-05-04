## INTEGRATOR AND DIFFERENTIATOR USING OP-AMP

---

### AIM

To design and simulate Integrator and Differentiator circuits using Op-Amp (µA741) and observe the output waveforms for square, triangular, and sine wave inputs.

---

### COMPONENTS / PARTS REQUIRED

| Component | Specification / Value |
|---|---|
| Op-Amp IC | µA741 (LM741) |
| Resistors | 15 kΩ (R1), 470 kΩ (R2), 15 kΩ (Rf) |
| Capacitors | 0.01 µF |
| Signal Generator | — |
| DC Power Supply | ±12 V |
| CRO / Output Meter | — |

**Virtual Lab Reference:** https://be-iitkgp.vlabs.ac.in/exp/operational-amplifier/theory.html

---

### THEORY

**Operational Amplifier (Op-Amp)** is a linear electronic device with three terminals: two high-impedance inputs and one output. It can perform multiple functions depending on the feedback combination (resistive, capacitive, or both). The ideal Op-Amp has infinite open-loop gain, infinite input impedance, zero output impedance, zero offset voltage, and infinite bandwidth.

#### INTEGRATOR

The integrator circuit is designed so that the output is proportional to the amplitude and duration of the input signal — it performs mathematical integration. The circuit is identical to an inverting amplifier, except the feedback resistor is replaced by a capacitor, making the circuit frequency-dependent.

When voltage is applied, the initially uncharged capacitor allows maximum current to flow. Due to virtual ground at the inverting input, no current flows into the Op-Amp. The capacitor charges at the rate of the RC time constant; as its impedance increases, the charging current decreases, producing a linearly increasing ramp output that continues until the capacitor is fully charged.

**Output voltage expression:**

$$V_o = -\frac{1}{RC} \int V_i \, dt + k$$

where $k$ is the constant of integration (depends on $V_o$ at $t = 0$).

The peak output voltage $V_T$ is given by:

$$V_T = \frac{VT}{4RC}$$

where $T$ is the time period of the input square wave.

> **Applications:** Analog computers, wave-shaping networks, ramp generators.

---

#### DIFFERENTIATOR

The differentiator circuit has its input connected to the inverting terminal of the Op-Amp through a capacitor (C), and negative feedback is provided through a resistor (Rf). It is essentially an integrator with the feedback capacitor and input resistor swapped.

The output is the first derivative of the input signal — 180° out of phase and amplified by a factor of $R_f \times C$. The input capacitor blocks DC and passes only AC. At low frequencies, capacitive reactance is high, resulting in low gain. At high frequencies, gain increases but the circuit becomes unstable and susceptible to noise.

**Output voltage expression:**

$$V_o = -R_f C_i \frac{dV_i}{dt}$$

The differentiator acts as a **high-pass filter**. At high frequencies it becomes unstable and may oscillate. Both stability and noise problems can be mitigated by adding a small series resistor $R_1$ in series with the input capacitor and a small capacitor $C_f$ in parallel with $R_f$ (practical differentiator).

---

### DESIGN

#### Design of Integrator

Given input frequency: **f = 1 kHz**

Unity gain frequency condition:

$$f = \frac{1}{2\pi R_1 C}$$

Let **C = 0.01 µF**, then:

$$R_1 = \frac{1}{2\pi \times 1000 \times 0.01 \times 10^{-6}} = 15.9 \, k\Omega \approx \mathbf{15 \, k\Omega \text{ (standard)}}$$

The resistor $R_2$ attenuates low-frequency signals and DC offset. Select $R_2 \geq 10 \times R_1$:

$$\mathbf{R_2 = 470 \, k\Omega}$$

---

#### Design of Differentiator

Given operating frequency: **f = 1 kHz**

$$f = \frac{1}{2\pi R_f C}$$

Let **C = 0.01 µF**, then:

$$R_f = \frac{1}{2\pi \times 1000 \times 0.01 \times 10^{-6}} = 15.9 \, k\Omega \approx \mathbf{15 \, k\Omega \text{ (standard)}}$$

---

### CIRCUIT DIAGRAMS

#### Fig. 3 – Integrator Circuit (LM741)

> _[Insert circuit diagram of Op-Amp Integrator here — R1 = 15 kΩ, R2 = 470 kΩ, C = 0.01 µF, ±12V supply]_

---

#### Fig. 4 – Differentiator Circuit (LM741)

> _[Insert circuit diagram of Op-Amp Differentiator here — C = 0.01 µF, Rf = 15 kΩ, ±12V supply]_

---

#### Fig. 5 – Practical Differentiator Circuit

> _[Insert practical differentiator circuit with R1 in series with C1 (input) and Cf in parallel with Rf, Rcomp = Rf || R1]_

---

### PROCEDURE

#### Integrator

1. Set up the integrator circuit as shown in Fig. 3. Apply a rectangular (square) wave of ±5 V (10 V peak-to-peak) at 1 kHz to the input. Observe both input and output simultaneously on the CRO.
2. Vary the DC offset of the square wave input and observe the change in the output waveform.
3. Repeat the experiment by feeding a **triangular wave** at the input. Observe and record the output.
4. Repeat the experiment by feeding a **sine wave** at the input. Observe and record the output.

#### Differentiator

1. Set up the differentiator circuit as shown in Fig. 4. Apply a rectangular (square) wave of ±5 V (10 V peak-to-peak) at 1 kHz to the input. Observe both input and output simultaneously on the CRO.
2. Repeat the experiment by feeding a **triangular wave** at the input. Observe and record the output.
3. Repeat the experiment by feeding a **sine wave** at the input. Observe and record the output.

---

### WAVEFORMS

#### Fig. 3 – Integrator Output (Square wave input → Triangular wave output)

> _[Insert waveform sketch / screenshot here — Input: Square wave Vi; Output: Triangular wave Vo]_

---

#### Fig. 4 – Differentiator Output (Square wave input → Pulse/spike output)

> _[Insert waveform sketch / screenshot here — Input: Square wave Vi; Output: Spike/impulse Vo]_

---

### DESIGN QUESTION

> _[Write the design question given by the instructor here]_

________________________________________________________________________

________________________________________________________________________

________________________________________________________________________

________________________________________________________________________

________________________________________________________________________

________________________________________________________________________

________________________________________________________________________

---

### CALCULATIONS

> _[Show step-by-step calculations for component values, peak output voltage VT, etc.]_

**Integrator – Peak Output Voltage:**

$$V_T = \frac{V \cdot T}{4RC}$$

Given: V = 5 V, T = 1 ms (f = 1 kHz), R = 15 kΩ, C = 0.01 µF

$$V_T = \frac{5 \times 1 \times 10^{-3}}{4 \times 15 \times 10^3 \times 0.01 \times 10^{-6}} = \frac{5 \times 10^{-3}}{600 \times 10^{-6}} \approx 8.33 \, V$$

**Differentiator – Output Voltage (for triangular input):**

$$|V_o| = R_f \cdot C \cdot \left|\frac{dV_i}{dt}\right|$$

________________________________________________________________________

________________________________________________________________________

________________________________________________________________________

---

### INPUT & OUTPUT WAVEFORMS (Graph Sheet)

> _[Attach or draw input and output waveforms on graph sheet for all three input types: Square, Triangular, Sine — for both Integrator and Differentiator]_

| Input Waveform | Integrator Output | Differentiator Output |
|---|---|---|
| Square Wave | Triangular Wave | Narrow Spikes / Impulses |
| Triangular Wave | Parabolic Wave | Square Wave |
| Sine Wave | Cosine Wave (inverted) | Cosine Wave |

---

### ANALYSIS

#### Frequency Response Analysis – Low Pass Filter (Integrator) & High Pass Filter (Differentiator)

> _[Perform AC sweep / frequency response simulation in PSPICE and attach Bode plots here]_

**LPF (Integrator) – Expected Bode Plot:**

> _[Insert Bode plot (Magnitude vs. Frequency) showing –20 dB/decade roll-off above cutoff frequency fc = 1/(2πRC)]_

Cutoff frequency:

$$f_c = \frac{1}{2\pi R_1 C} = \frac{1}{2\pi \times 15 \times 10^3 \times 0.01 \times 10^{-6}} \approx 1.06 \, kHz$$

---

**HPF (Differentiator) – Expected Bode Plot:**

> _[Insert Bode plot (Magnitude vs. Frequency) showing +20 dB/decade roll-off below cutoff frequency]_

Cutoff frequency:

$$f_c = \frac{1}{2\pi R_f C} = \frac{1}{2\pi \times 15 \times 10^3 \times 0.01 \times 10^{-6}} \approx 1.06 \, kHz$$

---

### RESULTS

The integrator and differentiator circuits using µA741 Op-Amp were designed, set up, and their outputs were observed for various input waveforms.

| Input | Integrator Output | Differentiator Output |
|---|---|---|
| Square wave (1 kHz, ±5V) | Triangular wave | Narrow pulses at transitions |
| Triangular wave | Parabolic / Sinusoidal wave | Square wave |
| Sine wave | Cosine wave (phase-shifted) | Cosine wave |

________________________________________________________________________

________________________________________________________________________

________________________________________________________________________

________________________________________________________________________

---

### INFERENCE

The Op-Amp integrator circuit produces an output that is the mathematical integral of the input signal. A square wave input yields a triangular wave, confirming that the integral of a constant is a ramp. The Op-Amp differentiator produces the mathematical derivative of the input; a square wave input gives narrow impulse spikes at each edge, confirming differentiation of step transitions.

The integrator behaves as a **low-pass filter** with a –20 dB/decade roll-off above the unity-gain frequency. The differentiator behaves as a **high-pass filter** with a +20 dB/decade gain rise with frequency, making it inherently unstable and noise-sensitive at high frequencies. The practical differentiator with series resistance and shunt capacitance limits the high-frequency gain, improving stability.

________________________________________________________________________

________________________________________________________________________

________________________________________________________________________

________________________________________________________________________

---

### VIRTUAL LAB REPORT

> _(Bonus marks — attach virtual lab report from https://be-iitkgp.vlabs.ac.in/exp/operational-amplifier/theory.html)_

> _[Attach virtual lab screenshots / PDF here]_

---

*Lab in Charges: Dr. Remya Jayachandran, Dr. Yajunath K, Dr. Sujeeth Rai K*
*The National Institute of Engineering, Mysuru — Department of ECE*
