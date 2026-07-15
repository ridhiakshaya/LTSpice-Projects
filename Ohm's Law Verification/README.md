# Ohm's Law Verification using LTspice

## Overview

This project demonstrates the verification of Ohm's Law (V = IR) using LTspice. A simple DC circuit consisting of a voltage source and a resistor is simulated to observe the relationship between voltage and current.

The experiment includes operating-point analysis, manual voltage variation, DC sweep analysis, and resistance variation to validate theoretical calculations against simulation results.

## Objectives

- Build a simple resistor circuit in LTspice.
- Verify Ohm's Law using Operating Point analysis.
- Compare theoretical and simulated current values.
- Perform a DC Sweep to observe the linear relationship between voltage and current.
- Study the effect of changing resistance on circuit current.


## Circuit Components

- DC Voltage Source (1–10 V)
- Resistor (1 kΩ, varied up to 10 kΩ)
- Ground

## Simulation Performed

- DC Operating Point (.op)
- DC Sweep (.dc)

## Results

## Observation Table

### 1. Voltage Variation (R = 1 kΩ)

| Voltage (V) | Calculated Current (mA) | Simulated Current (mA) |
|:-----------:|:-----------------------:|:----------------------:|
| 1  | 1  | 1  |
| 2  | 2  | 2  |
| 5  | 5  | 5  |
| 8  | 8  | 8  |
| 10 | 10 | 10 |

### 2. Resistance Variation (V = 10 V)

| Resistance (Ω) | Calculated Current (mA) | Simulated Current (mA) |
|:--------------:|:-----------------------:|:----------------------:|
| 500  | 20 | 20 |
| 1k   | 10 | 10 |
| 2k   | 5  | 5  |
| 5k   | 2  | 2  |


## Key Observations

- The simulated current closely matches the theoretical values calculated using Ohm's Law.
- Current increases linearly with applied voltage for a constant resistance.
- Increasing the resistance reduces the current inversely, as expected.

## Files Included

- LTspice schematic (.asc)
- Operating Point simulation results
- DC Sweep graph
- Simulation screenshots

## Learning Outcomes

This exercise provided practical experience with:

- Creating circuits in LTspice
- Running DC Operating Point simulations
- Performing DC Sweep analysis
- Comparing simulation results with theoretical calculations
- Understanding the relationship between voltage, current, and resistance
