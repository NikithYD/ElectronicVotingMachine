# Abstract
The overall idea of the project is to implement Automatic voting machine with ATmega328p as the main controller. The digital pins are connected to the 16x2 LCD Hd44780 
with 16 columns and 2 rows. LCD is used in 4 bit mode,i.e only D4-D7 of LCD is used inorder to save the pins of IC. Here the PIR sensor is mimicked using a switch is
pulled up to 5V. The pushbuttons are used as user input interface along with LEDs to indicate the status.

When the user enters the vicinity of the machine, green LED starts blinking with WELCOME message. The user can cast the vote as soon as the message to cast the vote 
appears by pressing the button provided for atleast 1 sec. The voter will not have any idea about the total count. Only the organizer can access this information throgh 
special switch where the total count status is displayed on LCD. Thus the design helps in smooth and efficient management of the voting process with minimum human intervention.
