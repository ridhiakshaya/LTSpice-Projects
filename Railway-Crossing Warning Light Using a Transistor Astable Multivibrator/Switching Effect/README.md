**Sequence of Operation**

The operation of the transistor astable multivibrator was analysed using the collector voltage, base voltage, and LED current waveforms obtained from LTspice.

1. Initial Switching at Power-On

When the 9 V supply is applied, the two transistors are never perfectly identical due to slight differences in transistor parameters and capacitor charging conditions. As a result, one transistor begins conducting slightly before the other, initiating the oscillation.

2. Collector Voltage Drives the Opposite Transistor

As one transistor switches ON, its collector voltage rapidly falls from approximately 9 V to nearly 0 V. Through the coupling capacitor, this sudden voltage change applies a negative pulse to the base of the opposite transistor, driving it into cutoff.

3. Capacitor Charging Process

Once a transistor is OFF, the coupling capacitor connected to its base begins charging through the corresponding 47 kΩ base resistor. The base voltage therefore increases gradually with an exponential charging waveform until it reaches the transistor's turn-on voltage.

4. Switching OFF of the Conducting Transistor

As the opposite capacitor charges, the OFF transistor's base voltage eventually reaches approximately 0.7 V, causing it to switch ON. Simultaneously, its collector voltage falls, sending a negative pulse through the opposite coupling capacitor that removes the base drive from the previously conducting transistor, forcing it to switch OFF.

5. Positive Feedback and Continuous Oscillation

The cross-coupled capacitors provide positive feedback, ensuring that once one transistor begins switching, the other is driven rapidly into the opposite state. This regenerative action produces fast transitions and continuous oscillation without any external clock signal.

6. Complementary LED Currents

Each LED is connected in the collector circuit of one transistor. Consequently, when Q1 conducts, LED1 carries current while LED2 remains OFF. When Q2 conducts, the opposite occurs. The LED current waveforms are therefore complementary, with one LED ON whenever the other is OFF, producing the alternating railway warning light effect.
