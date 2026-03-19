# DC-Motor-Direction-Control-Using-8051

## Aim:
To implement a DC Motor Direction Control Using 8051.

## Apparatus Required:
•	Laptop with Keil uVision software
•	Proteus Design Suite

## Algorithm:
1. Start the program.
2. Open C program text file.
3. Type the program.
4. Select the hex file creation before building the program.
5.Build/compile the program.
6. Start debugging.
7. Open Proteus Software & design circuit as per circuit diagram.
8. Copy the hex file to 8051 controller.
9.Simulate the circuit in Proteus software.

## Program :
```
ORG 0000H       ; 

START:
    ; Motor Forward (P1.0 = 1, P1.1 = 0)
    SETB P1.0
    CLR  P1.1
    ACALL DELAY

    ; Motor Stop (Both LOW)
    CLR  P1.0
    CLR  P1.1
    ACALL DELAY

    ; Motor Reverse (P1.0 = 0, P1.1 = 1)
    CLR  P1.0
    SETB P1.1
    ACALL DELAY

    ; Motor Stop
    CLR  P1.0
    CLR  P1.1
    ACALL DELAY

    SJMP START   ; 
DELAY:
    MOV R2, #20
D1: MOV R1, #255
D2: MOV R0, #255
D3: DJNZ R0, D3
    DJNZ R1, D2
    DJNZ R2, D1
    RET

END
```
<img width="1920" height="1200" alt="Screenshot 2026-03-18 225535" src="https://github.com/user-attachments/assets/4d3d8dd0-2ef6-4d45-acd7-200246c4c462" />

## Output :
<img width="1920" height="1200" alt="Screenshot 2026-03-18 225446" src="https://github.com/user-attachments/assets/be3eb03e-ee80-4ac9-82fb-70e8fffa2e27" />


## Result:
The DC Motor direction control using 8051 microcontroller has been successfully implemented and simulated using Keil and Proteus.

