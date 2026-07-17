# Analysis of Common Emitter BJT Amplifier using LTspice

## Overview

This project presents the simulation and analysis of a **Common Emitter (CE) BJT Amplifier** using **LTspice**. The amplifier was designed to study transistor biasing, voltage amplification, frequency response, clipping characteristics, and the effect of the emitter bypass capacitor on voltage gain.

The project includes **DC Operating Point Analysis**, **Transient Analysis**, **Voltage Gain Comparison**, **Clipping Analysis**, and **AC Frequency Response (Bode Plot)** to evaluate the amplifier's performance under different operating conditions.

---

## Objectives

* Design and simulate a Common Emitter BJT Amplifier.
* Determine the transistor's DC operating point.
* Measure the input and output waveforms.
* Compare voltage gain with and without the emitter bypass capacitor.
* Observe output clipping for different input amplitudes.
* Determine the amplifier's frequency response and bandwidth using AC analysis.

---

# Experiment 1: Circuit Design

### Objective

Construct the Common Emitter BJT Amplifier using LTspice with proper biasing and coupling capacitors.

### Components Used

| Component                     |          Value |
| ----------------------------- | -------------: |
| Transistor                    |         2N3904 |
| Supply Voltage                |           12 V |
| Collector Resistor (RC)       |         2.2 kΩ |
| Emitter Resistor (RE)         |           1 kΩ |
| Bias Resistors                |   47 kΩ, 10 kΩ |
| Input Capacitor               |          10 µF |
| Output Capacitor              |          10 µF |
| Emitter Bypass Capacitor (CE) |         100 µF |
| Load Resistor                 |          10 kΩ |
| Input Signal                  | SINE(0 20m 1k) |

---

# Experiment 2: DC Operating Point Analysis

### Objective

Determine the transistor's DC bias voltages and operating current to verify that it operates in the active region.

### Observation Table

| Parameter                       |        Value |
| ------------------------------- | -----------: |
| Base Voltage (VB)               |  **2.069 V** |
| Emitter Voltage (VE)            |  **1.407 V** |
| Collector Voltage (VC)          |  **8.915 V** |
| Collector Current (IC)          | **1.402 mA** |
| Collector-Emitter Voltage (VCE) |  **7.508 V** |

### Observation

The transistor is correctly biased in the **active region**, making it suitable for linear amplification.

---

# Experiment 3: Transient Analysis

### Objective

Observe the input and output waveforms and verify the voltage amplification and phase inversion.

### Observations

* The output signal is amplified with respect to the input.
* The output waveform is **180° out of phase** with the input signal, confirming the operation of the Common Emitter configuration.

---

# Experiment 4: Voltage Gain Analysis

### Objective

Compare the voltage gain of the amplifier with and without the emitter bypass capacitor (CE).

### Observation Table

| Condition  | Vin (mV) | Vout (Vpp) |      Gain | Remarks                                                                              |
| ---------- | -------: | ---------: | --------: | ------------------------------------------------------------------------------------ |
| With CE    |       40 |      3.845 | **96.13** | High gain due to AC bypass of the emitter resistor.                                  |
| Without CE |       40 |    0.07054 | **1.763** | Low gain due to emitter negative feedback caused by the unbypassed emitter resistor. |

### Observation

The emitter bypass capacitor significantly increases the amplifier gain by bypassing the emitter resistor for AC signals, thereby reducing emitter degeneration (negative feedback).

---

# Experiment 5: Clipping Analysis

### Objective

Investigate the effect of increasing the input signal amplitude on the output waveform.

### Observation Table

| Input (mV) | Output (Vpp) | Clipping          | Remarks                                                                       |
| ---------: | -----------: | ----------------- | ----------------------------------------------------------------------------- |
|         20 |         3.85 | No clipping       | Undistorted amplified sine wave.                                              |
|         50 |         9.79 | Slight clipping   | Output waveform begins to flatten at the peaks.                               |
|        100 |        10.01 | Moderate clipping | Output waveform is noticeably distorted with flattened peaks.                 |
|        200 |        10.04 | Severe clipping   | Output waveform is heavily distorted due to transistor saturation and cutoff. |

### Observation

As the input amplitude increases, the amplifier eventually reaches its operating limits. The transistor enters saturation and cutoff during different portions of the signal cycle, resulting in output waveform clipping.

---

# Experiment 6: AC Analysis (Bode Plot)

### Objective

Determine the frequency response and bandwidth of the amplifier.

### Observation Table

| Parameter                   |        Value |
| --------------------------- | -----------: |
| Midband Gain                |  **33.6 dB** |
| Lower Cutoff Frequency (fL) | **30.76 Hz** |
| Upper Cutoff Frequency (fH) |  **> 1 MHz** |
| Bandwidth                   |  **> 1 MHz** |

### Observation

The amplifier exhibits a nearly constant gain over the mid-frequency range. The gain decreases at low frequencies due to the coupling and bypass capacitors, while the upper cutoff frequency exceeds the simulated frequency range of 1 MHz.

---

# Key Observations

* The transistor operates in the active region with proper DC biasing.
* The Common Emitter configuration provides **180° phase inversion** between the input and output signals.
* The emitter bypass capacitor substantially increases voltage gain by reducing AC negative feedback.
* Increasing the input amplitude causes output clipping due to transistor saturation and cutoff.
* The amplifier exhibits good midband gain and a wide bandwidth suitable for voltage amplification applications.

---

# Conclusion

The Common Emitter BJT Amplifier was successfully designed and analyzed using LTspice. The simulation verified proper transistor biasing, voltage amplification, phase inversion, and the influence of the emitter bypass capacitor on gain. Clipping analysis demonstrated the limitations of the amplifier at higher input amplitudes, while AC analysis confirmed a stable midband gain of **33.6 dB** and a bandwidth exceeding **1 MHz** within the simulated range. The results closely align with the theoretical behavior of a Common Emitter amplifier, demonstrating its effectiveness as a voltage amplifier for small-signal applications.

---
