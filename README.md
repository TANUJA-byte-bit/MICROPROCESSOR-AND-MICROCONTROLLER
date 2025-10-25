7.Write an assembly language program in 8051 to generate a 200 us delay using Timer 0 in Mode 1 and toggle an LED connected to Port 0.1.

## Aim
To develop an 8051 microcontroller assembly program that uses Timer 0 in Mode 1 to generate a 200 us delay and toggles an LED connected to Port 0.1.

## Apparatus Required

8051 Microcontroller Trainer Kit (or simulator like Keil uVision, Proteus, or 8051 IDE)
LED (connected to Port 0.1)
10kΩ Resistor (as current limiter)
Connecting Wires & Breadboard (for practical hardware)
Computer with IDE/Assembler for code development and simulation

## Algorithm

Set Port 0.1 as output.
Initialize Timer 0 in Mode 1 (16-bit mode).
Load the Timer registers to generate a 200 us delay.
Start Timer 0 and wait until the overflow flag is set (TF0 = 1).
Stop the timer and clear overflow flag.
Toggle the state of Port 0.1.
Repeat steps 3–6 indefinitely

## Program
#include <reg51.h>

sbit mybit = P1 ^ 5;     

void T0M1Delay_200us(void);

void main(void)
{
    TMOD = 0x01;         
    TR0  = 0;            
    TF0  = 0;            

    while (1)
    {
        mybit = ~mybit;      
        T0M1Delay_200us();   
    }
}
void T0M1Delay_200us(void)
{
    TH0 = 0xFF;   
    TL0 = 0x48;  
    TF0 = 0;      
    TR0 = 1;     

    while (TF0 == 0);   

    TR0 = 0;      
    TF0 = 0;    
}


## Output
<img width="1920" height="1200" alt="Screenshot (3461)" src="https://github.com/user-attachments/assets/747fd06f-9730-4d0c-afc4-1e5c76afa974" />
<img width="1920" height="1200" alt="Screenshot (3460)" src="https://github.com/user-attachments/assets/57215fe8-f6fc-4b9a-abfa-84807a524b17" />

## Result
Successfully designed and verified an 8051 Assembly program to toggle an LED at Port 0.1 with a precise 200 us interval using Timer 0 in Mode 1.
Demonstrated timer initialization, delay loop, and I/O port manipulation in 8051 Assembly.






