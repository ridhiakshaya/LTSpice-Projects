**Railway-Warning Design**

The astable multivibrator was redesigned to function as a railway-crossing warning light, producing alternating flashes between two LEDs. The design objective was to achieve a stable oscillation frequency of approximately 1 Hz, ensuring that each LED remained ON for about 0.5 s while maintaining a 50% duty cycle. Standard resistor and capacitor values were selected to satisfy the design requirements and were verified through LTspice transient simulations.

## Design Specifications

| Specification | Target |
|---------------|--------|
| **Supply Voltage** | 9 V DC |
| **LED1 ON Time** | ≈ 0.5 s |
| **LED2 ON Time** | ≈ 0.5 s |
| **Total Oscillation Period** | ≈ 1 s |
| **Oscillation Frequency** | ≈ 1 Hz |
| **LED Current** | 8–12 mA |
| **Duty Cycle** | ≈ 50% |
| **Component Selection** | Standard resistor and capacitor values only |

**Design Calculations**

For a symmetrical transistor astable multivibrator, the half-cycle time is approximated by

t=0.69RC

To obtain an LED ON time of approximately 0.5 s, the required RC time constant was first calculated. The nearest commercially available resistor and capacitor values were then selected and verified through simulation.

| Parameter | Calculated Value | Selected Standard Value | Simulated Value |
|-----------|-----------------:|------------------------:|----------------:|
| **RB1 = RB2** | 72.5 kΩ | 68 kΩ | 68 kΩ |
| **C1 = C2** | 10.65 µF | 10 µF | 10 µF |
| **LED Current-Limiting Resistor** | 680 Ω | 680 Ω | 680 Ω |
| **Half-cycle Time** | 0.50 s | — | 0.47 s |
| **Total Period** | 1.00 s | — | 0.94 s |
| **Frequency** | 1.00 Hz | — | 1.07 Hz |


**Design Verification**

The final circuit closely met the required design specifications:

The simulated oscillation frequency was 1.07 Hz, which falls within the specified 1 Hz ±10% range.
Each LED remained ON for approximately 0.47 s, producing nearly equal ON and OFF intervals.
The measured period of 0.94 s resulted in an almost 50% duty cycle.
The LED current remained within the required 8–12 mA range using 680 Ω current-limiting resistors.
Both transistors alternated between cutoff and saturation, producing clean complementary collector voltage and LED current waveforms.
The circuit began oscillating immediately after the supply was applied, demonstrating reliable self-starting behaviour.

Overall, the redesigned circuit successfully satisfied the railway-warning design requirements while using only standard component values, making it suitable for practical implementation as a simple alternating warning light controller.
