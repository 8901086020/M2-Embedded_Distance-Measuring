## Connections Between AVR & HC-SR04

- TRIG pin can be connected to any GPIO pin, and that pin will work as output from the MCU
- ECHO pin is connected to INT0 pin (PD2), to use INT0 to detect changes in the echo output when going from LOW-to-HIGH to start counting the pulse width, and when going from       HIGH-  to-LOW to stop counting the pulse width and take the counted pulse_width value and translates it into a distance
