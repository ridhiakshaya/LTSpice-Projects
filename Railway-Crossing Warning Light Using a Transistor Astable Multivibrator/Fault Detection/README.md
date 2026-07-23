# Fault Investigation

To better understand the operation of the astable multivibrator, several common fault conditions were intentionally introduced into the circuit. Before running each simulation, the expected behaviour was predicted based on the circuit operation. The predictions were then verified using LTspice transient analysis.

The investigation demonstrates the importance of the RC feedback network, transistor switching, and LED orientation in maintaining continuous oscillation.

## Fault Analysis Summary

| Fault Condition | Effect on Oscillation | Effect on LEDs | Cause |
|-----------------|----------------------|----------------|-------|
| **C1 disconnected** | Oscillation stops | One LED remains ON while the other remains OFF | Feedback path is interrupted, preventing regenerative switching. |
| **C2 short-circuited** | Oscillation stops | One LED remains continuously ON | Capacitor cannot charge or discharge, so transistor switching cannot occur. |
| **RB1 = 1 MΩ** | Oscillation slows down | LEDs continue alternating with a much longer flash interval | Increased RC time constant delays capacitor charging. |
| **Q2 removed** | No oscillation | LED2 remains OFF and LED1 stays in a fixed state | One half of the multivibrator is removed, breaking the feedback loop. |
| **LED1 reversed** | Oscillation unaffected | LED1 never lights while LED2 flashes normally | Reverse-biased LED blocks current but does not affect the transistor switching network. |

## Discussion

The fault analysis clearly shows that the capacitors, base resistors, and transistors form the regenerative feedback network responsible for producing continuous oscillations. Any fault that interrupts this feedback path causes the circuit to stop oscillating or significantly alters the flashing frequency. In contrast, reversing an LED affects only the visual output and does not prevent the transistors from switching, since the LED is not directly involved in the feedback mechanism.

This investigation highlights the critical role of each component in the operation of a transistor astable multivibrator and demonstrates how component failures influence circuit performance.
