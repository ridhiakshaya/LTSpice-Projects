#  Railway-Crossing Warning Light using a Transistor Astable Multivibrator

## Overview

This project demonstrates the design and simulation of a **Railway-Crossing Warning Light** using a transistor-based astable multivibrator in **LTspice**. The circuit generates two complementary square-wave outputs that alternately flash two LEDs, emulating the operation of railway crossing warning lights.

It investigates how resistor and capacitor values influence the oscillation characteristics, redesigns the circuit to satisfy a given design specification, and analyses the effect of common circuit faults on the multivibrator's operation.

---

## Objectives

* Design and simulate a transistor astable multivibrator.
* Generate alternating flashes using two LEDs.
* Study the effect of capacitance on oscillation period and flashing frequency.
* Study the effect of base resistance on flashing frequency.
* Design the circuit to satisfy a railway-warning specification.
* Analyse circuit behaviour under different fault conditions.

---

## Components

|   Component                                               |            Specification            |
| --------------------------------------------------------- | ----------------------------------- |
|   Supply Voltage                                          | 9 V DC                              |
|   Q1, Q2                                                  | 2N3904                              |
|   RB1, RB2                                                | 47 kΩ                               |
|   LED Current-Limiting Resistors                          | 680 Ω                               |
|   C1, C2                                                  | 10 µF                               |
|   LED1, LED2                                              | Red LEDs                            |


---

# Working Principle

The circuit consists of two NPN transistors connected in a cross-coupled configuration using RC networks. As one transistor switches ON, the other switches OFF. The capacitors charge and discharge alternately through the base resistors, continuously reversing the transistor states and producing complementary square-wave outputs. This causes the LEDs to flash alternately.

---

# Effect of Capacitance

With the base resistors fixed at **47 kΩ**, the capacitor values were varied to observe their effect on the oscillation characteristics.

| C1 = C2 | Measured Period (s) | Frequency (Hz) | Approx. LED ON Time (s) |
| ------: | ------------------: | -------------: | ----------------------: |
|  4.7 µF |              0.3125 |           3.20 |                   0.156 |
|   10 µF |               0.625 |           1.60 |                   0.312 |
|   22 µF |                1.43 |           0.69 |                   0.715 |
|   47 µF |                3.33 |           0.30 |                    1.67 |

### Calculations

* **Period (T)** = Simulation Time / Number of Complete Cycles
* **Frequency (f)** = 1 / T
* **Approximate LED ON Time** = T / 2

### Observation

Increasing the capacitance increased the RC time constant, causing the capacitors to charge and discharge more slowly. As a result, the oscillation period and LED ON time increased, while the flashing frequency decreased.

### Conclusion

The flashing rate is **inversely proportional to the capacitance** when the base resistance is kept constant.

---

# Effect of Base Resistance

With **C1 = C2 = 10 µF**, the base resistors were varied while observing the flashing rate.

| RB1 = RB2 | Measured Period (s) | Frequency (Hz) | Remarks          |
| --------: | ------------------: | -------------: | ---------------- |
|     22 kΩ |               0.333 |           3.00 | Fastest Flashing |
|     47 kΩ |               0.625 |           1.60 | Moderate         |
|     68 kΩ |               0.833 |           1.20 | Slower           |
|    100 kΩ |                1.25 |           0.80 | Slowest Flashing |

### Observation

Increasing the base resistance slowed the charging and discharging of the capacitors, increasing the oscillation period and reducing the flashing frequency.

### Conclusion

The flashing rate is **inversely proportional to the base resistance** when the capacitance is kept constant.

---

# Railway-Warning Design

The circuit was redesigned to satisfy the following specifications:

* LED1 ON time ≈ **0.5 s**
* LED2 ON time ≈ **0.5 s**
* Total period ≈ **1 s**
* Frequency ≈ **1 Hz**
* LED current between **8 mA and 12 mA**
* Duty cycle ≈ **50%**

## Design Calculations

The half-cycle time of a symmetrical astable multivibrator is approximated by

[
t = 0.69RC
]

Selected component values were chosen using standard resistor and capacitor values and verified through simulation.

| Parameter       | Calculated Value | Selected Standard Value | Simulated Value |
| --------------- | ---------------: | ----------------------: | --------------: |
| RB1 = RB2       |          72.5 kΩ |                   68 kΩ |           68 kΩ |
| C1 = C2         |         10.65 µF |                   10 µF |           10 µF |
| LED Resistor    |            680 Ω |                   680 Ω |           680 Ω |
| Half-cycle Time |           0.50 s |                       — |          0.47 s |
| Total Period    |           1.00 s |                       — |          0.94 s |
| Frequency       |          1.00 Hz |                       — |         1.07 Hz |

The final design satisfied the required specifications while using only standard component values.

---

# Fault Investigation

The circuit was tested under different fault conditions to study the importance of each component in maintaining oscillation.

| Fault Introduced          | Prediction                                                                  | Simulated Result                                               |
| ------------------------- | --------------------------------------------------------------------------- | -------------------------------------------------------------- |
| C1 disconnected           | The feedback path is broken, so the circuit stops oscillating.              | One LED remains ON while the other stays OFF.                  |
| C2 short-circuited        | The capacitor cannot charge and discharge, preventing transistor switching. | The circuit latches in one state with one LED continuously ON. |
| RB1 increased to 1 MΩ     | The capacitor charges more slowly, reducing the flashing rate.              | The LEDs continue flashing with a much longer period.          |
| Q2 removed                | The feedback loop is broken, preventing oscillation.                        | LED2 remains OFF and LED1 stays in a fixed state.              |
| LED1 connected in reverse | LED1 cannot conduct because it is reverse-biased.                           | LED1 remains OFF while LED2 continues flashing normally.       |

---

# Results

* Successfully implemented a transistor astable multivibrator in LTspice.
* Generated complementary outputs to alternately drive two LEDs.
* Verified the effect of capacitance and base resistance on oscillation frequency.
* Designed a railway-warning circuit operating close to **1 Hz** with an approximately **50% duty cycle**.
* Investigated the behaviour of the circuit under common fault conditions.

---

## Learning Outcomes

Through this project, I gained practical experience in designing and analysing transistor-based astable multivibrators, selecting standard component values to meet timing specifications, interpreting transient waveforms in LTspice, and understanding how RC networks influence oscillation frequency and duty cycle. I also explored how common circuit faults affect the operation of an astable multivibrator and verified these behaviours through simulation. This project strengthened my understanding of transistor switching circuits, timing analysis, and practical electronic circuit design.
