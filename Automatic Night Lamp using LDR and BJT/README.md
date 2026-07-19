# Automatic Night Lamp using LDR and BJT 

An LTspice implementation of an **Automatic Night Lamp** using an **LDR (Light Dependent Resistor)** and a **2N3904 NPN transistor**. The circuit automatically turns the LED **OFF during bright conditions** and **ON during darkness** by sensing changes in ambient light through the LDR.

---

## Objective

The objectives of this experiment are to:

* Design and simulate an automatic night lamp using an LDR and BJT.
* Study transistor operation under bright and dark conditions.
* Determine the switching threshold of the circuit by sweeping the LDR resistance.
* Calculate and verify the LED current-limiting resistor.
* Redesign the circuit to satisfy a given set of design specifications.

---

## Components Used

| Component           |                           Value |
| ------------------- | ------------------------------: |
| Supply Voltage      | 12 V DC (9 V for redesign task) |
| Transistor          |                    2N3904 (NPN) |
| LED                 |                    Standard LED |
| Fixed Resistor (R1) |          10 kΩ (initial design) |
| Base Resistor (RB)  |                          4.7 kΩ |
| LED Resistor (RLED) |                           680 Ω |
| LDR                 |       Variable (1 kΩ to 100 kΩ) |


---

# Experiment 1: Bright and Dark Condition Analysis

The LDR resistance was changed to represent different lighting conditions and the operating point of the circuit was observed.

## Observation Table

|   RLDR | Lighting Condition | VB (V) | VC (V) | VCE (V) |      IB |      IC | LED |
| -----: | ------------------ | -----: | -----: | ------: | ------: | ------: | :-: |
|   1 kΩ | Bright             |  0.118 | 11.815 |  11.815 |     0 A |     0 A | OFF |
| 100 kΩ | Dark               |  0.732 |  11.27 |   11.27 | 96.3 μA | 16.4 mA |  ON |

### Bright Condition (RLDR = 1 kΩ)

The LDR resistance is low, producing a base voltage below 0.7 V. The transistor remains in cutoff, so no collector current flows and the LED stays OFF.

### Dark Condition (RLDR = 100 kΩ)

The LDR resistance increases, raising the base voltage to about 0.7 V. The transistor turns ON (saturation), allowing current through the LED and turning it ON.

### Conclusion

The circuit successfully distinguishes between bright and dark conditions. A low LDR resistance keeps the transistor OFF, while a high LDR resistance provides enough base bias to switch the transistor ON and illuminate the LED.

---

# Experiment 2: Determining the Switching Threshold

The LDR value was swept using:

```text
.step param RLDR list 1k 2k 5k 10k 20k 50k 100k
```

## Observation Table

| RLDR (Ω) | VB (V) |       IB (A) |        IC (A) | LED Current ID (A) | LED Status | Transistor Region |
| -------: | -----: | -----------: | ------------: | -----------------: | :--------: | :---------------: |
|       1k |  0.118 |            0 |             0 |       1.30 × 10⁻¹¹ |     OFF    |       Cutoff      |
|       2k |  0.235 | 1.09 × 10⁻¹¹ | 1.110 × 10⁻¹⁰ |      1.141 × 10⁻¹⁰ |     OFF    |       Cutoff      |
|       5k |  0.571 | 1.252 × 10⁻⁷ |  4.162 × 10⁻⁵ |       4.163 × 10⁻⁵ |     OFF    |       Active      |
|      10k |  0.711 | 2.753 × 10⁻⁵ |  8.486 × 10⁻³ |       8.486 × 10⁻³ |     ON     |     Saturation    |
|      20k |  0.731 | 5.937 × 10⁻⁵ |  1.628 × 10⁻² |       1.628 × 10⁻² |     ON     |     Saturation    |
|      50k |  0.732 | 8.591 × 10⁻⁵ |  1.638 × 10⁻² |       1.638 × 10⁻² |     ON     |     Saturation    |
|     100k |  0.733 | 9.629 × 10⁻⁵ |  1.639 × 10⁻² |       1.639 × 10⁻² |     ON     |     Saturation    |

### Conclusion

As the LDR resistance increased, the base voltage also increased. The transistor began conducting around **5 kΩ** and entered saturation near **10 kΩ**, turning the LED ON. Therefore, the switching threshold of the circuit is approximately **6-7 kΩ**.

---

# Experiment 3: Effect of Fixed Divider Resistor (R1)

The LDR was fixed at **20 kΩ** while the fixed divider resistor (R1) was varied.

## Observation Table

| R1 (kΩ) | VB (V) |       IB (A) |       IC (A) | LED Current ID (A) |  LED Status |
| ------: | -----: | -----------: | -----------: | -----------------: | :---------: |
|     4.7 |  0.758 | 1.053 × 10⁻³ | 1.650 × 10⁻² |       1.650 × 10⁻² |      ON     |
|      10 |  0.747 | 6.381 × 10⁻⁴ | 1.648 × 10⁻² |       1.648 × 10⁻² |      ON     |
|      22 |  0.739 | 3.278 × 10⁻⁴ | 1.646 × 10⁻² |       1.646 × 10⁻² |      ON     |
|      47 |  0.734 | 1.521 × 10⁻⁴ | 1.642 × 10⁻² |       1.642 × 10⁻² |      ON     |
|     100 |  0.731 | 5.937 × 10⁻⁵ | 1.628 × 10⁻² |       1.628 × 10⁻² | ON (Dimmer) |

### Conclusion

Increasing R1 reduced the available base current, but the transistor still remained in saturation. The LED current changed only slightly, indicating that the circuit continues to operate reliably over a wide range of R1 values.

---

# Experiment 4: LED Current-Limiting Resistor Design

### Given

* Supply Voltage = **12 V**
* LED Forward Voltage = **2 V**
* Desired LED Current = **15 mA**
* Transistor Saturation Voltage = **0.2 V**

### Calculation

Voltage across resistor:

V_R = 12 - 2 - 0.2 = 9.8 V

Resistor value:

R = 9.8/0.015 = 653.3 Ω

Nearest standard resistor:

**680 Ω**

## Observation Table

| Parameter                     |    Value |
| ----------------------------- | -------: |
| Supply Voltage                |     12 V |
| LED Forward Voltage           |      2 V |
| Desired LED Current           |    15 mA |
| Transistor Saturation Voltage |    0.2 V |
| Calculated Resistance         |  653.3 Ω |
| Selected Standard Resistor    |    680 Ω |
| Simulated LED Current         | 16.39 mA |

### Conclusion

The calculated resistor value was **653.3 Ω**, and the nearest standard value of **680 Ω** was selected. LTspice produced an LED current of approximately **16.39 mA**, which is close to the design target and confirms the resistor selection.

---

# Experiment 5: Circuit Redesign

## Design Requirements

* 9 V supply
* LED turns ON when RLDR > 30 kΩ
* LED current between 10 mA and 15 mA
* Transistor operates in saturation
* Divider current below 1 mA
* Standard resistor values

## Final Component Values

| Component           |  Value |
| ------------------- | -----: |
| Supply Voltage      |    9 V |
| R1                  |  22 kΩ |
| RB                  | 4.7 kΩ |
| RLED                |  560 Ω |
| RLDR (Switch Point) |  30 kΩ |

## Verification

| Requirement              | Required     | Obtained             |
| ------------------------ | ------------ | -------------------- |
| Supply Voltage           | 9 V          | 9 V                  |
| LED ON when RLDR > 30 kΩ | RLDR = 30 kΩ | LED ON               |
| LED Current              | 10-15 mA     | 14.63 mA             |
| Transistor Saturation    | VCE ≤ 0.2 V  | 0.0807 V             |
| Divider Current          | < 1 mA       | 0.321 mA             |
| Standard Resistors       | Yes          | 22 kΩ, 4.7 kΩ, 560 Ω |

### Conclusion

The circuit was redesigned for a 9 V supply using a 22 kΩ fixed resistor, a 4.7 kΩ base resistor, and a 560 Ω LED current-limiting resistor. LTspice verification showed that at an LDR resistance of 30 kΩ, the LED turned ON with a current of 14.63 mA, which lies within the specified range of 10-15 mA. The transistor operated in saturation with a collector-emitter voltage of approximately 0.08 V, and the sensing-divider current remained well below 1 mA. Therefore, the redesigned circuit satisfies all the given design specifications. 

---

# Overall Conclusion

This project demonstrates how an LDR and an NPN transistor can be used to build a simple and reliable automatic night lamp. Through LTspice simulations, the circuit behavior was analyzed under different lighting conditions, the switching threshold was identified, the LED current-limiting resistor was designed and verified, and the circuit was successfully redesigned to meet specific engineering constraints. The results closely matched the expected theoretical operation, making the design suitable as a basic light-controlled switching circuit.

---

**Key Concepts:** LDR, Automatic Night Lamp, BJT Switching, 2N3904, Voltage Divider, LED Driver, Saturation Region, Cutoff Region, LTspice Simulation, Analog Electronics.
