# Design of a 5.1 V Regulated Power Supply using a Zener Diode

## Project Overview

This project presents the design and simulation of a 5.1 V regulated DC power supply using a bridge rectifier, capacitor filter, and Zener diode voltage regulator in LTspice. The objective was to study the operation of each stage of the regulated power supply and evaluate its performance through transient simulations.

The project demonstrates the complete conversion of an AC input into a stable regulated DC output while analyzing the effects of rectification, filtering, ripple voltage, load regulation, and line regulation.


## Objectives

* Design a full-wave bridge rectifier.
* Convert AC voltage into DC using full-wave rectification.
* Reduce ripple using a smoothing capacitor.
* Regulate the output voltage using a 5.1 V Zener diode.
* Study the influence of filter capacitance on ripple voltage.
* Analyze load regulation by varying the load resistance.
* Analyze line regulation by varying the input AC voltage.


## Circuit Specifications

| Parameter        | Value           |
| ---------------- | --------------- |
| AC Input         | 12 V RMS, 50 Hz |
| Bridge Rectifier | 1N4007 Diodes   |
| Filter Capacitor | 470 µF          |
| Series Resistor  | 330 Ω           |
| Zener Diode      | 5.1 V           |
| Load Resistance  | 1 kΩ (Nominal)  |



# Tasks Performed

## Task 1 - Rectification

A full-wave bridge rectifier was designed using four **1N4007** diodes. The transient response was simulated to observe the conversion of the sinusoidal AC input into a full-wave rectified waveform.

### Result

* Successful full-wave rectification obtained.
* Output frequency doubled from **50 Hz** to **100 Hz**.

---

## Task 2 - Ripple Analysis

The effect of filter capacitance on ripple voltage was investigated by varying the smoothing capacitor while measuring the maximum voltage, minimum voltage, and ripple voltage.

### Observation Table

| Capacitance (µF) | Vmax (V) | Vmin (V) | Ripple Voltage (V) |
| ---------------: | -------: | -------: | -----------------: |
|              100 |    15.52 |    13.38 |               2.14 |
|              470 |    15.36 |    14.82 |               0.54 |
|             1000 |    15.41 |    15.09 |               0.32 |

### Observation

Increasing the filter capacitance significantly reduced the ripple voltage, resulting in a smoother DC output.

---

## Task 3 - Output Voltage and Current Measurements

The regulated output voltage and branch currents were measured under nominal operating conditions.

Measured parameters:

* Output Voltage = 5.108 V
* Series Resistor Current = 30.07 mA
* Load Current = 5.108 mA
* Zener Current = 25.678 mA

These measurements verified proper current sharing between the load and the Zener diode.

---

## Task 4 - Load Regulation

The load resistance was varied while maintaining a constant input voltage to evaluate the load regulation performance of the Zener regulator.

### Observation Table

| Load Resistance (Ω) | Output Voltage (V) | Load Current (mA) | Zener Current (mA) |
| ------------------: | -----------------: | ----------------: | -----------------: |
|               2.2 k |              5.109 |             2.322 |             28.459 |
|                 1 k |              5.108 |             5.108 |             25.678 |
|                 680 |              5.107 |             7.510 |             23.279 |
|                 470 |              5.105 |            10.861 |             19.933 |
|                 330 |              5.102 |            15.460 |             15.343 |

### Observation

As the load resistance decreased, the load current increased while the Zener current decreased. The output voltage remained approximately **5.1 V**, demonstrating effective load regulation.


## Task 5 - Line Regulation

The AC input voltage was varied while monitoring the regulated output voltage.

### Observation Table

| Input Voltage (RMS) (V) | Peak Voltage (V) | Output Voltage (V) |
| ----------------------: | ---------------: | -----------------: |
|                       9 |            12.72 |              5.100 |
|                      12 |            16.97 |              5.108 |
|                      15 |            21.21 |              5.113 |

### Observation

The regulated output voltage remained nearly constant despite variations in the input voltage, demonstrating good line regulation.


# Key Learning Outcomes

* Designed a full-wave bridge rectifier in LTspice.
* Implemented capacitor-based ripple filtering.
* Simulated a Zener diode voltage regulator.
* Performed transient analysis and waveform interpretation.
* Studied the effect of filter capacitance on ripple voltage.
* Evaluated load regulation characteristics.
* Evaluated line regulation characteristics.
* Measured node voltages and branch currents using LTspice waveform analysis.


# Project Files
---
├── Schematic (.asc)
├── Ripple Effect Waveforms
├── Load Regulation Waveforms
├── Line Regulation Waveforms
├── Observation Tables
└── README.md
---


