<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

The project consists of a state machine with 4 outputs, which is used to control a bipolar stepper motor. El número de pulsos aplicados es la distancia que recorre el eje y la frecuencia con que aplicamos los pulsos, es directamente proporcional a la  velocidad de giro. Asimismo un nivel alto aplicado en la entrada DIR hace que el motor gire en sentido horario, mientras que una señal a nivel bajo hace que el eje se mueva en sentido antihorario.

Otras entradas son:

La entrada /RESET pone el driver en un estado inicial predefinido  y apaga las salidas. Todos los pulsos aplicados en la entrada STEP se ignoran hasta que la entrada /RESET se pone a nivel alto.

/ENABLE. Cuando se aplica valor lógico alto (3.3 - 5V) las salidas se desactivan. Cuando se aplica un 0 el control interno habilita las salidas.

/SLEEP. Modo de reposo. Para minimizar el consumo de energía cuando el motor no está en uso, esta entrada desactiva gran parte de la circuitería interna. Un nivel lógico bajo en el pin SLEEP pone al A4988 en modo de reposo.

MS1, MS2, MS3. Microstep Resolution, desde full step hasta 1/16 micropasos. Para full-step poner todos los pines a GND. 

## How to test

The system has an external clock input, a reset input, a control input for selecting the direction of rotation of the motor, an enable input and 4 outputs for the stepper motor coils.

## External hardware

The system requires an external clock input to control the speed of the pulses and thus regulate the rotation speed of the motor.
