# Pen-Plotter-Arduino-Shield

## This is a Pen Plotter Arduino Shield to be used with an Uno R3 Arduino.

This shield is designed to work with an Arduino that has been loaded with GRBL 0.9. All electrical pin definitions are the default pin assignments specified in the 0.9 version of the code. N.B, servo PWM control uses PIN D11 (the Z-Limit signal). A couple notes about this shield:

- This shield is a modification of the original CNC shield. There is no Z-axis motor control. An AGFRC A20CLS servo is being used to move the pen up and down. This high torque (7.5 kg-cm) servo runs on a voltage between 4.8 Volts and 8.4 Volts. To generate a 5.0 servo voltage, from the 12 V stepper motor power supply, a LM2596 buck switching regulator is used. The maximum 3 A output is enough to adequately drive the A20CLS motor. I was unable to find a maximum stall current specification for this particular servo, but the assumption is that it is a least an amp.

- The Y-axis is driven by two mirrored stepper motors, so this shield ties these control signals together on the board, rather than using a jumper. This saves some board space.

- Adding a 10 A fuse to the board to protect the 12 V power supply if a short occurs on the shield. Place it so it can actually be serviced more easily.
- Group all connectors together to increase accessibility.
- Make limit switch connections 3 conductors, instead of 2 conductors. The OpenBuilds limit switches are a three wire interface.
- Remove jumper connections to EN, STEPS, DIRS. It is not necessary to expose these. Remove jumper connections to SPNEN, SPNDIR, COOLEN (these are unused by the pen plotter). Remove header to UART signals, SPI, and power connections. All of these removals will free up board space.
- Make mounting screw hole locations accessible.
