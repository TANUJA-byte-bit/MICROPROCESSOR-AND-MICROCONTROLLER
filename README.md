3.Write an assembly language program in 8051 to generate a 2 ms delay using Timer 0 in Mode 1 and toggle an LED connected to Port 2.0.

## Aim
To develop an 8051 microcontroller assembly program that uses Timer 0 in Mode 1 to generate a 2 ms delay and toggles an LED connected to Port 2.0.

## Apparatus Required

8051 Microcontroller Trainer Kit (or simulator like Keil uVision, Proteus, or 8051 IDE)
LED (connected to Port 2.0)
10kΩ Resistor (as current limiter)
Connecting Wires & Breadboard (for practical hardware)
Computer with IDE/Assembler for code development and simulation

## Algorithm

Set Port 2.0 as output.
Initialize Timer 0 in Mode 1 (16-bit mode).
Load the Timer registers to generate a 2 ms delay.
Start Timer 0 and wait until the overflow flag is set (TF0 = 1).
Stop the timer and clear overflow flag.
Toggle the state of Port 2.0.
Repeat steps 3–6 indefinitely

## Program
#include<reg51.h>

void delay():
void main (){
P2 = 0x00;
while (1)
P2 = 0xFF:
delay () ;
P2 = 0x00;
delay () ;
void delay (){
int i;
for(i = 0; i <= 5000; 1++)
}
}

## Output
![WhatsApp Image 2025-10-14 at 18 59 31_d3b9b86e](https://github.com/user-attachments/assets/0e5bb11c-b443-4b54-a974-3de2539847c4) 

## Result
Successfully designed and verified an 8051 Assembly program to toggle an LED at Port 2.0 with a precise 2 ms interval using Timer 0 in Mode 1.
Demonstrated timer initialization, delay loop, and I/O port manipulation in 8051 Assembly.






