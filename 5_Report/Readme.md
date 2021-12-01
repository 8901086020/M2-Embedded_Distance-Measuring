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

# 4W's and 1'H :-

# What
An ultrasonic sensor is an instrument that measures the distance to an object using ultrasonic sound waves. An ultrasonic sensor uses a transducer to send and receive      ultrasonic pulses that relay back information about an object's proximity.

# Where
  It is used everywhere including in industry likely used in drone.

# When
  It has to be deployed 2nd december2021

# Why
  I am using this because it is used by blind people so s that they are not collide by any thing and it can be used in their stick.


# How
  I am using C programming language for Developing this distance measuring project using ultrasonic sensor.

## HIGH LEVEL REQUIREMENTS:-
| ID | Description |  
| ----- | ----- | 
|HLR01|Used to avoid and obstacles with robots like biped robot, obstacle avoider robot, path finding robot etc 
|HLR02|Used to measure the distance within a wide range of 2cm to 400cm
|HLR03|Depth of certain places like wells,pits etc can be measured since the waves can penetrate through water


## LOW LEVEL REQUIREMENTS:-
| ID | Description | 
| ----- | ----- |
|LLR01|Power Supply:5v Dc  
|LLR02|Measuring Angle:30 degree
|LLR03|Trigger input pulse width:10uS TTL pulse
|LLR04|Depth of certain places like wells pits etc can be measured since the waves can penetrate through water
## Connections Between AVR & HC-SR04

- TRIG pin can be connected to any GPIO pin, and that pin will work as output from the MCU
- ECHO pin is connected to INT0 pin (PD2), to use INT0 to detect changes in the echo output when going from LOW-to-HIGH to start counting the pulse width, and when going from       HIGH-  to-LOW to stop counting the pulse width and take the counted pulse_width value and translates it into a distance

  ![embedded img](https://user-images.githubusercontent.com/63248297/144100791-69ff18b8-4e4f-4145-9371-58758fd19cd8.JPG)
   
   ![embedded img2](https://user-images.githubusercontent.com/63248297/144189652-3d7117b6-58da-40ea-bf5a-ffcbd71314b6.JPG)

![embedded img1](https://user-images.githubusercontent.com/63248297/144189902-0b28a0e6-b9ef-4566-87fa-143ab4e9969c.JPG)

