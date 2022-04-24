# Hardware Implementation

* Custom Made PCB
For the purpose of eliminating the need of using six visible wires, an adaptation at the level of the motor controller board has been made. The pins used to control the direction of the motor, as well as the enabling (IN1, IN2, IN3, IN4, ENA, ENB) have been disordered and soldered back to the opposite part of the board, in order to fit the custom made PCB. The custom made PCB comes with four groups of female headers sockets with the purpose of extending the available pins of the Arduino. The fifth horizontal socket is used just as a support for the motor controller.

# Software Implementation

The programming language used for implementation is Embedded C which is considered to be a high level assembly language. Embedded C language have been chosen for having the possibility to write the code in Atmel Studio which allows ports manipulation, working with bits and timers, interrupts and embedded system concepts.

The resulted HEX file from the compilation was uploaded to the microcontroller bootloader using Xloader software.


