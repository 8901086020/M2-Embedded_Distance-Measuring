## Connections Between AVR & HC-SR04
- TRIG pin can be connected to any GPIO pin, and that pin will work as output from the MCU
- ECHO pin is connected to INT0 pin (PD2), to use INT0 to detect changes in the echo output when going from LOW-to-HIGH to start counting the pulse width, and when going from       HIGH-to-LOW to stop counting the pulse width and take the counted pulse_width value and translates it into a distance


  ![embedded img](https://user-images.githubusercontent.com/63248297/144100791-69ff18b8-4e4f-4145-9371-58758fd19cd8.JPG)   
   ![embedded img2](https://user-images.githubusercontent.com/63248297/144189652-3d7117b6-58da-40ea-bf5a-ffcbd71314b6.JPG)
