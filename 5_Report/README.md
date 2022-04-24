# Obsatcle Avoidance Vehicle Using ATmega328P Microcontroller (Arduino)

* Introduction: Obsatcle Avoidance Vehicle Using ATmega328P Microcontroller (Arduino)
Obstacle Avoidance Vehicle capable of detecting objects, scanning the area and navigating through the less obstructed path.

# Step 1: Materials Needed

# Hardware
* Arduino UNO based on ATmega328 microcontroller
* DYP-ME007 ultrasonic sensor
* Servomotor
* L298N Dual H-Bridge Motor driver
* Power Supply - i used LiPo 2s 4000 mAH
* 2x DC motors with 298:1 metal gearbox
* LED
* Chasis
* 2 back wheels and one front omnidirectional ball wheel

# Software
* Atmel Studio
* XLoader software

# Tools
* Solder iron
* Desolder pump
* PCB's
* Jumper Wires

# Step 2: Hardware Implementation
The LED is used to visually illustrate the fact that the sensor detected an object.

The schematic of the chasis can be found here:

https://www.instructables.com/id/Line-following-robot-with-PID-algorithm/

# Diagram

All the electrical connection are presented in the diagram.

Custom Made PCB

For the purpose of eliminating the need of using six visible wires, an adaptation at the level of the motor controller board has been made. The pins used to control the direction of the motor, as well as the enabling (IN1, IN2, IN3, IN4, ENA, ENB) have been disordered and soldered back to the opposite part of the board, in order to fit the custom made PCB. The custom made PCB comes with four groups of female headers sockets with the purpose of extending the available pins of the Arduino. The fifth horizontal socket is used just as a support for the motor controller.

# Step 3: Software Implementation
The programming language used for implementation is Embedded C which is considered to be a high level assembly language. Embedded C language have been chosen for having the possibility to write the code in Atmel Studio which allows ports manipulation, working with bits and timers, interrupts and embedded system concepts.

The resulted HEX file from the compilation was uploaded to the microcontroller bootloader using Xloader software.

# Algorithm
The algorithm is presnted in the figure.

1) Enable motors

2) Scan

3) Is distance to obstacle greater than 20 cm?

a) If yes = > move forward

b) If no:

b.i) Stop, scan left side and store left distance in a variable

b.ii) Scan right side and store right distance in another variable

b.iii) Are the two distances smaller than 5 cm? (By subtrating the two distances the robot is able to get out of a corner without being stuck)

(b.iii.1) If yes => turn around and move forward

(b.iii.2) If no:

(b.iii.2.a) Is right distance smaller than left distance?

(b.iii.2.a.i) If yes => turn left and move forward

(b.iii.2.a.ii) If no => turn right and move forward

Add TipAsk QuestionCommentDownload
Step 4: Step 4: the Code
For a better understanding of the code is recommended to check the ATmega32P microncontroller datasheet.

The software implementation for the ultrasonic sensor was done with the help of the Arduino libraries.
