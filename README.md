# Avr_Ultrasonic
  An ATMega328p based project that reads distance using ultrasonic sensor module, and displays it on Graphical LCD
## Introduction:-   
   The ultrasonic module used is the 4-pin HC-SR04, can be found here: https://www.sparkfun.com/products/13959.

   Its sensing range is 2cm to 400cm

   It has VCC, GND pins for powering the module, and 2 pins to interface with the microcontroller.

   Pins used with the MCU are:

   1.Trigger: The MCU has to put a pulse of 10-to-15 usec to initiates a distance reading process

   2.Echo: The module sends a pulse on this pin to the MCU, width of the pulse determines distance between the sensor and the obstacle in its sensing range.

## Ultrasonic module main idea
   The ultrasonic module is a transceiver, it has to ultrasonic speaker, one acting as a ultrasonic transmitting speaker and the other acting as an ultrasonic receiving mic        (sensor). When a trigger is given to the module it sends a sound signal on the transmitting one, and put HIGH on the echo pin waiting until a signal is received back on the      sensing mic or a time_out happens:

   1.If no obstacle exist, the receiving sensor won't sense any signal, and the module will time_out representing no signal retrieved.

   2.If an obstacle exists, the receiving sensor will sense the returning echo signal, as the sound wave will hit the obstacle and come back to the ultrasonic sensor, here the        ultrasonic module will put LOW on the echo pin to represent time taken starting from sending the signal until it has hit the obstacle and came all the way back to the            module again, so the time will represent time taken by the signal to pass the distance between the ultrasonic module and the obstacle twice. Using Speed of Sound, and            getting time taken by the signal, distance can be easily calculated.

     As sound_speed = 34300 cm/sec

     and time_one_way = pulse_time / 2; // where time_one_way = total time calculated by the sensor (pulse_time) divided by 2

     distance can be calculated as:

     distance = sound_speed * time_one_way;

     As time calculations will be in micro-seconds:

     sound_speed = 0.0343 cm/usec

     distance = 0.0343 * pulse_time / 2;

## Swot Analysis

 
**STRENGTHS**   
  
   Ultrasonic sensors reflect sound off of objects, so the color or transparency have no effect on the sensor’s reading.
  
**WEAKNESSES**  

   Ultrasonic sensors operate using sound, they are completely nonfunctional in a vacuum as there is no air for the sound to travel through.

**OPPORTUNITIES**    

  The tech-based market has a huge opportunities in capturing the youth market. And this ultrasonic sensor based distance measuring is a one step further in future.


**THREATS**  

  The slower growth in technological innovation will also bring a significant threat in the upcoming dynamic world.

#### CI and Code Quality

|Build|Cppcheck|Codacy|
|:--:|:--:|[![Codacy Badge](https://app.codacy.com/project/badge/Grade/a1d7b4943f0043759d5dfcf2d8fdbc73)](https://www.codacy.com/gh/8901086020/M2-Embedded_Distance-Measuring/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=8901086020/M2-Embedded_Distance-Measuring&amp;utm_campaign=Badge_Grade)|
