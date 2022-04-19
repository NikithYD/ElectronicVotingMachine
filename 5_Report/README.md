# Project Report on Voting Machine

## Introduction
The project is based on microcontroller based EVM. Electronic Voting Machine 
helps in fast and efficient counting. It helps in smooth management of the voting 
process and tracking the overall operations. In the project, controller used is 
ATmega 328p which performs and controls the working of the model. In order
to display the status, 16×2 Liquid crystal display is used. Users are given the 
opportunity to select the candidate, the data can be used for later purpose.
EVMs greatly reduce the human effort to count individual cotes. The EVMs are 
produced with secure manufacturing practices, and by design, are self contained, battery-powered and lack any networking capability. The first voting 
machines were mechanical but it is increasingly more common to use electronic 
voting machines. Voting machines differ in usability, security, cost, speed, 
accuracy, and ability of the public to oversee elections. Machines may be more 
or less accessible to voters with different disabilities.

## Objectives
The design and implementation is divided into different objectives and 
outcomes. Below are the list of objectives-
 * To move closer to the working area
 * To vote for the candidate of one’s choice
 * To retrieve the stored data
 
## Component Analysis
 ### ATmega 328p
ATmega328P is high performance, low power controller from Microchip. 
ATmega328P is an 8-bit microcontroller based on AVR RISC architecture. It is the 
most popular of all AVR controllers as it is used in ARDUINO boards. It has 14 
digital I/O pins, of which 6 can be used as PWM outputs and 6 analog input pins. 
These I/O pins account for 20 of the pins.
### HD44780 LCD
In the 1980s, Hitachi developed the HD44780 LCD controller, a Dot matrix liquid 
crystal display (LCD) controller with alphanumeric digits. The controller's 
character set contains ASCII characters, Japanese Kana characters, and some 
symbols in two 28-character lines.
### Pushbuttons
A push switch (button) is a momentary or non-latching switch which causes a 
temporary change in the state of an electrical circuit only while the switch is 
physically actuated. After a circuit is interrupted, an automatic mechanism (i.e. 
a spring) returns the switch to its default position, restoring the initial condition 
of the circuit.

## Block diagram
![BlOCK](https://user-images.githubusercontent.com/68335075/164075793-03349239-163c-4013-9175-f66ed10edf32.png)
 ### Working and Methodology
 Initially, the user has to move close to the sensing region of the PIR sensor which 
primarily detects the motion. Note that in Simulide simulation, switch pulled up 
to 5V is used to mimic the sensor. Whenever the motion is detected, 
corresponding high signals are fed to the controller. The switch is connected to 
the digital pin of the IC. 
The LCD initially shows the greeting messages. As the switch is on( indicating 
motion detected), blinking of the green LED starts along with the message 
written to the display “Please cast your valuable vote”. The register select, 
enable and register write pins of LCD is connected to pin 5,7 and 6 respectively 
of PORTD of the IC. The data pins D4 –D7 is connected to B4 – B7 digital pins of 
IC respectively. The LCD display operates in 4 bit mode.
Pushbuttons are connected to C0 –C4 of the IC (ADC pins). The pins are pulled 
up using 5V supply and 10k ohm resistor. Other end is connected to ground. 
Hence when switch is pressed the logic level switches from 5V to 0V, providing 
a switching action. This action is read by the controller and used to count the 
number of times the button pressed. The LED pins are connected to B0 –B2
digital pins of the IC.
When the user press the button, the count variable stores the data. Each switch 
associated with different counts depending on the user. This data obtained is 
passed to the LCD by first converting it to string, stored in variable using itoa 
function and then sent to LCD .
The “lcdcmd” function sends the necessary commands for initialization in 4 bit 
mode. The “lcd_init” initializes the LCD and the “lcddata” function sends the 
string data to the LCD to which strings are passed by the lcd_print function. “sei”
is used to initialize the all the global flags.

## Results and Conclusions
![Screenshot (1247)](https://user-images.githubusercontent.com/68335075/164076088-b2dcf271-ddc6-453a-8bed-2548b7960ff2.png)

The code (.hex) file is uploaded to the designed circuit in Simulide and working 
is observed. Among the most important benefits is the elimination of the need 
to print millions of ballot papers, as only one ballot paper needs to be attached 
to the Balloting Unit at each polling place instead of one ballot paper for each 
elector. Thus in countries like India, where population is in billions, 
accommodating ballot papers is a difficult task and requires cutting of trees 
which affects the environment. Manual labour and stress can be reduced and it 
will be flexible to implement as well as to get the results based on voting
