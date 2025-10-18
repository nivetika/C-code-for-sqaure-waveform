# C-code-for-sqaure-waveform
## Aim
To Write a 8051 c program to generate a square wave with frequency of 50khz.
--

## Apparatus Required
- Personal Computer  
- Keil µVision software  
---

## Algorithm
1. **Start the program.**
2. **Initialize Timer 0** in Mode 1 (16-bit).
3. **Main Loop (infinite)**:
   - Set Port 1 HIGH.
   - Call `delay()` to hold the HIGH state.
   - Set Port 1 LOW.
   - Call `delay()` to hold the LOW state.
   - Repeat indefinitely to create a square wave.
4. **Delay Function**:
   - Load TH0 and TL0 with initial values.
   - Start Timer 0.
   - Wait until Timer Overflow Flag (TF0) is set.
   - Stop Timer 0 and clear TF0.
   - Return to main loop.
5. **End** (the program runs indefinitely).
---

## Program
```
#include <reg51.h>  
void delay(void);  
void main(void)
{
    TMOD = 0x01;  
    while(1)
    {
        P1 = 0xFF;  
        delay();   
        P1 = 0x00;  
        delay();
    }
}
void delay(void)
{
    TH0 = 0xFF;    
    TL0 = 0xFA;     
    TR0 = 1;       
    while (TF0 == 0);
       TR0 = 0;        
       TF0 = 0;  
}
```

## Output
![WhatsApp Image 2025-10-18 at 12 52 30_551a6a69](https://github.com/user-attachments/assets/2e484e5f-5bbf-47a7-9b9a-06f584974ecc)

## Result
Thus To Write a 8051 c program to generate a square wave with frequency of 50khz was done using 8051 keil software.
      
