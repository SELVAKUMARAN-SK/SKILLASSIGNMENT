#SKILL ASSIGNMENT-1

PROGRAM:
Write an assembly language program in 8051 to reverse the elements of an array and store the reversed array in another memory location.

APPARATUS REQUIRED:

LAPTOP WITH KEIL SOFTWARE

PROGRAM:
```
ORG 0000H

; initialize array elements
MOV 30H, #11H
MOV 31H, #22H
MOV 32H, #33H
MOV 33H, #44H
MOV 34H, #55H

MOV R0, #30H     ; source start address
MOV R1, #40H     ; destination start address
MOV R2, #05H     ; total 5 elements

; point R0 to last element (30H + 4)
MOV A, R0
ADD A, #04H
MOV R0, A

BACK: MOV A, @R0
      MOV @R1, A
      DEC R0
      INC R1
      DJNZ R2, BACK

HERE: SJMP HERE   ; stop program

END
```
INPUT:
![WhatsApp Image 2025-10-30 at 2 45 05 PM](https://github.com/user-attachments/assets/b5d5bcac-8fab-4035-ada6-0e448e0ec9ac)

OUTPUT:
![WhatsApp Image 2025-10-30 at 2 51 38 PM](https://github.com/user-attachments/assets/b97f509f-4377-4e48-a297-632f2c26520a)



RESULT:

Thus the  language program in 8051 to reverse the elements of an array and store the reversed array in another memory location.
