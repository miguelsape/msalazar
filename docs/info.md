<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

The project consists of a state machine with 4 outputs, which is used to control a bipolar stepper motor. The number of pulses applied is the distance that the axis travels and the frequency with which we apply the pulses is directly proportional to the rotation speed. Likewise, a high level applied to the DIR input causes the motor to rotate clockwise, while a low level signal causes the axis to move counterclockwise.

Other entries are:

The /RESET input puts the driver into a predefined initial state and turns off the outputs. All pulses applied to the STEP input are ignored until the /RESET input is set high.

/ENABLE. When a high logic value is applied the outputs are deactivated. When a 0 is applied, the internal control enables the outputs.

/SLEEP. Sleep mode. To minimize power consumption when the motor is not in use, this input disables much of the internal circuitry. A low logic level on the SLEEP pin puts the A4988 into sleep mode.

MS1, MS2, MS3. Microstep Resolution, from full step to 1/16 microsteps. For full-step put all the pins to GND.

## How to test

The system has an external clock input, a reset input, a control input for selecting the direction of rotation of the motor, an enable input and 4 outputs for the stepper motor coils.

Bidirectional pins
uio[0]: "Output Bit 0"
uio[1]: "Output Bit 1"
uio[2]: "Output Bit 2"
uio[3]: "Output Bit 3"
uio[4]: "enable"
uio[5]: "direction"

## External hardware

The system requires an external clock input to control the speed of the pulses and thus regulate the rotation speed of the motor.
