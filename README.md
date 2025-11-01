#SKILL ASSIGNMENT-2

PROGRAM:

 Write an assembly language program in 8051 to generate a 500 µs delay using Timer 0 in Mode 2 and toggle Port 1.3.

APPARATUS REQUIRED:

LAPTOP WITH KEIL SOFTWARE

PROGRAM:
```
ORG 0000H

START:  MOV TMOD, #02H      ; Timer0 in Mode2 (8-bit auto-reload)
        MOV TH0, #06H       ; Reload = 06H -> 256-06H = 250 ticks per overflow
        MOV TL0, #06H       ; initial TL
        CLR TF0             ; clear Timer0 overflow flag
        SETB TR0            ; start Timer0

MAIN:   MOV R5, #00         ; overflow counter = 0

WAIT1:  JNB TF0, WAIT1      ; wait until TF0 = 1 (overflow)
        CLR TF0             ; clear TF0
        INC R5

        CJNE R5, #02, WAIT1 ; need 2 overflows for 500 µs (2 * 250 = 500)
        MOV R5, #00

        CPL P1.3            ; toggle P1.3
        SJMP MAIN

        END
     
```
INPUT:
![WhatsApp Image 2025-10-30 at 2 51 50 PM](https://github.com/user-attachments/assets/daa89261-acbe-455f-b126-73da8ec6c016)

OUTPUT:
![WhatsApp Image 2025-10-30 at 2 51 50 PM](https://github.com/user-attachments/assets/036cf3e1-5d60-42c5-b601-f36f3d90156d)

RESULT:

Thus an assembly language program in 8051 to generate a 500 µs delay using Timer 0 in Mode 2 and toggle Port 1.3.
