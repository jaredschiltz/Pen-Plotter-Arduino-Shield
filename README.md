# Pen-Plotter-Arduino-Shield

## This is a Pen Plotter Arduino Shield to be used with an Uno R3 Arduino. Rev A

This shield is designed to work with an Arduino that has been loaded with GRBL 0.9. All electrical pin definitions are the default pin assignments specified in the 0.9 version of the code. N.B, servo PWM control uses PIN D11 (the Z-Limit signal). Pen-up command is M03 S255 and Pen-down command is M03 S0. With the current firmware, the angle delta between S255 and S0, is 90 degrees. A couple notes about this shield:

- This shield is a modification of the original CNC shield. There is no Z-axis motor control. An AGFRC A20CLS servo is being used to move the pen up and down. This high torque (7.5 kg-cm) servo runs on a voltage between 4.8 Volts and 8.4 Volts. To generate a 5.0 servo voltage, from the 12 V stepper motor power supply, a LM2596 buck switching regulator is used. The maximum 3 A output is enough to adequately drive the A20CLS motor. I was unable to find a maximum stall current specification for this particular servo, but the assumption is that it is a least an amp.
- The Y-axis is driven by two mirrored stepper motors, so this shield ties these control signals together on the board, rather than using a jumper. This saves some board space.
- Change glass fuse to PPTC resettable fuse. Fuse specs: 16 V, 8 A hold, 13.6 A trip
- Remove 10K pullup on enable signal. Each driver board has a built-in 20K pullup.
- Make limit switch connections 3 conductors, instead of 2 conductors. The OpenBuilds limit switches are a three wire interface.
- Remove jumper connections to EN, STEPS, DIRS. It is not necessary to expose these. Remove jumper connections to SPNEN, SPNDIR, COOLEN (these are unused by the pen plotter). Remove header to UART signals, SPI, and power connections. All of these removals will free up board space.
- Make mounting screw hole locations accessible.

The following changes should be made to Rev A:

- No changes need to be implemented to date

Parts list:
|Designator |Designation |MFG |MFG Part No. |Supplier|Supplier Part No. |Quantity|
|----------------------|------------------------------------------------------------------------------------------|---------------------------|-----------------------|--------|-------------------------------|--------|
|J3 |Vertical Connector Header, 2-Pos, 2.54 mm, 6 mm contact length |Wurth Elektronik |61300211121 |Digikey |732-5315-ND |1 |
|J4/J23,J22/J19,J20/J21|Vertical Connector Header, 2-Pos, 2.54 mm, 6 mm contact length |Wurth Elektronik |61300421121 |Digikey |732-5294-ND |3 |
|D1 |1N5824 5 A Schottky Diode |Vishay |SB520-E3/54 |Digikey |SB520-E3/54GICT-ND |1 |
|C2,C1,C3 |100uF 50 V |Panasonic |EEU-FM1H101B |Digikey |P19712CT-ND |3 |
|J6,J2,J1,J10,J7,J9 |8 Position Header Connector 0.100" (2.54mm) Through Hole |Sullins Connector Solutions|PPTC081LFBN-RC |Digikey |S7006-ND |6 |
|J5,J8,J11 |Vertical Connector Header, 4-Pos, 2.54 mm, 6 mm contact length |Wurth Elektronik |61300411121 |Digikey |732-5317-ND |3 |
|U1 |IC REG BUCK LM2596 5V 3A TO263-5 |UMW |LM2596S-5.0 |Digikey |4518-LM2596S-5.0CT-ND |1 |
|C5,C4 |330 uF, 50V, Low-ESR 58 m-ohm |Kemet |ESW337M050AH4EA |Digikey |399-6661-1-ND |2 |
|L1 |33 uH, 3.6 A, 51 m-Ohm |Abracon LLC |AIUR-06-330K |Digikey |AIUR-06-330K-ND |1 |
|J13 |2 Position Wire to Board Terminal Block Horizontal with Board 0.197" (5.00mm) Through Hole|Wurth Elektronik |691137710002 |Digikey |732-10955-ND |1 |
|J14,J15,J16,J12,J17 |Vertical Connector Header, 3-Pos, 2.54 mm, 6 mm contact length |Wurth Elektronik |61300311121 |Digikey |732-5316-ND |5 |
|J18 |Vertical Connector Header, (2 Rows / 6-Pos), 2.54 mm, 6 mm contact length |Wurth Elektronik |61300621121 |Digikey |732-5295-ND |1 |
|U3 |Vertical Connector Header, 6-Pos, 2.54 mm, 6 mm contact length |Wurth Elektronik |61300611121 |Digikey |732-5319-ND |1 |
|U2, U7 |Vertical Connector Header, 8-Pos, 2.54 mm, 6 mm contact length |Wurth Elektronik |61300811121 |Digikey |732-5321-ND |1 |
|U6 |Vertical Connector Header, 10-Pos, 2.54 mm, 6 mm contact length |Wurth Elektronik |61301011121 |Digikey |732-2670-ND | |
|F1 |PPTC Radial Resettable Fuse (8.0 A Hold Current, 13.5 A Trip Current, 16 V Max) |RFE/Fuzetec |FRG800-16F |Digikey |3451-FRG800-16F-ND |1 |
|S1 |MOMENTARY-SWITCH-SPST-PTH-6.0MM |CUI Devices |TS02-66-60-BK-160-LCR-D|Digikey |2223-TS02-66-60-BK-160-LCR-D-ND|1 |
|H3 |M3 Mounting Hole | | | | |1 |
