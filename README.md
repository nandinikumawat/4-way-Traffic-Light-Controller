# Intelligent Traffic Light Controller with Countdown Timer

## Introduction

Traffic congestion is a critical issue in modern cities worldwide, leading to various problems such as time loss, missed opportunities, and increased frustration. This project addresses traffic congestion by designing an Intelligent Traffic Light Controller using the 8051 microcontroller. The system features a countdown timer to provide drivers with real-time information about the remaining time to the next traffic light state.

## Aim

The primary goal of this project is to create a traffic light controller that optimizes traffic flow, reduces congestion, and enhances overall road safety. The implementation involves the use of 8051 microcontroller, 7-segment displays, LEDs, and a countdown timer to achieve these objectives.

## Implementation

### Components Used

1. **8051 Microcontroller:** Intel's 8-bit microcontroller with 40 pins, featuring on-chip crystal oscillator (12MHz) and 4KB ROM.
2. **7-Segment Displays (Common Anode):** Used to display the countdown timer and provide real-time information to drivers.
3. **LEDs:** Serve as indicators for the traffic lights.
4. **Crystal (12MHz):** Provides the external frequency for the microcontroller.
5. **Other Components:** Push button, capacitors, resistors, traffic lights module.

![image](https://github.com/nandinikumawat/4-way-Traffic-Light-Controller/assets/63352345/dd9410ba-4771-4a60-810e-b690de7d6d44)

### Code

The assembly code for the 8051 microcontroller is provided in the `CODE` section of the README. It includes the logic for controlling the traffic lights and countdown timer based on specific conditions.

ORG 00H
LJMP MAIN
ORG 300H

TBL: DB 0C0H,0F9H,0A4H,0B0H,99H,92H,82H,0F8H,80H,90H ; 7-seg data for comm. anode type
ORG 30H

MAIN: MOV P2, #00H
      MOV P3, #00H
      ACALL FRONT
      MOV DPTR, #TBL
      CLR A
      MOV 40H, #10
      MOV 43H, #10
      MOV 46H, #20
      MOV 49H, #20
      MOV R0, #35
      MOV R6, #30
      MOV R7, #40

X1:   MOV A, 40H
      MOV B, #10
      DIV AB
      MOV 41H, A
      MOV 42H, B

A1:   SETB P3.0
      CLR P3.1
      MOV A, 41H
      MOVC A, @A+DPTR
      MOV P2, A
      ACALL DELAY
      MOV P3, #00H
      SETB P3.1
      CLR P3.0
      MOV A, 42H
      MOVC A, @A+DPTR
      MOV P2, A
      ACALL DELAY
      MOV P3, #00H
      SJMP X3

X2:   SJMP X1
X3:   MOV A, 43H
      MOV B, #10
      DIV AB
      MOV 44H, A
      MOV 45H, B
      SETB P3.2
      CLR P3.3
      MOV A, 44H
      MOVC A, @A+DPTR
      MOV P2, A
      ACALL DELAY
      MOV P3, #00H
      SETB P3.3
      CLR P3.2
      MOV A, 45H
      MOVC A, @A+DPTR
      MOV P2, A
      ACALL DELAY
      MOV P3, #00H
      MOV A, 46H
      MOV B, #10
      DIV AB
      MOV 47H, A
      MOV 48H, B
      SETB P3.4
      CLR P3.5
      MOV A, 47H
      MOVC A, @A+DPTR
      MOV P2, A
      ACALL DELAY
      MOV P3, #00H
      SETB P3.5
      CLR P3.4
      MOV A, 48H
      MOVC A, @A+DPTR
      MOV P2, A
      ACALL DELAY
      MOV P3, #00H
      MOV A, 49H
      MOV B, #10
      DIV AB
      MOV 50H, A
      MOV 51H, B
      SETB P3.6
      CLR P3.7
      MOV A, 50H
      MOVC A, @A+DPTR
      MOV P2, A
      ACALL DELAY
      MOV P3, #00H
      SETB P3.7
      CLR P3.6
      MOV A, 51H
      MOVC A, @A+DPTR
      MOV P2, A
      ACALL DELAY
      MOV P3, #00H
      DJNZ R0, X2
      MOV R0, #35
      DJNZ 40H, Q1
      MOV 40H, #20
      
Q1:   DJNZ 43H, Q2
      MOV 43H, #10
      ACALL RIGHT

Q2:   DJNZ 46H, Q3
      MOV 43H, #20
      MOV 46H, #10

Q3:   DJNZ 49H, Q4
      MOV 49H, #10
      ACALL BACK

Q4:   DJNZ R6, X4
      ACALL LEFT
      MOV 40H, #10
      MOV 43H, #10
      MOV 46H, #30

X4:   DJNZ R7, L1
      LJMP MAIN
L1:   LJMP X1

DELAY: MOV R4, #5
      H2: MOV R5, #0FFH
          H1: DJNZ R5, H1
              DJNZ R4, H2
              RET

FRONT: MOV P1, #54H
       MOV P0, #02H
       RET

RIGHT: MOV P1, #0A1H
       MOV P0, #02H
       RET

BACK:  MOV P1, #09H
       MOV P0, #05H
       RET

LEFT:  MOV P1, #4AH
       MOV P0, #08H
       RET

       
### Interfacing Diagram

A diagram illustrating the connections between the microcontroller and other components is included in the README to help users understand the hardware setup.

![image](https://github.com/nandinikumawat/4-way-Traffic-Light-Controller/assets/63352345/7fb7eccc-ee39-4065-ab52-4b62750f72c9)

### Simulations

Simulated results of the traffic light controller in action, including different traffic scenarios and countdown timer functionality.

![image](https://github.com/nandinikumawat/4-way-Traffic-Light-Controller/assets/63352345/9002d140-7dc2-4069-84f7-5ce6375c9970)

![image](https://github.com/nandinikumawat/4-way-Traffic-Light-Controller/assets/63352345/12397e34-6af7-446f-9741-d3ebe3c58ee1)

![image](https://github.com/nandinikumawat/4-way-Traffic-Light-Controller/assets/63352345/2306fb6b-9c29-4c46-a313-3776fc2f3a5b)

![image](https://github.com/nandinikumawat/4-way-Traffic-Light-Controller/assets/63352345/876cd552-55e9-4444-adce-532b2555d3a9)

## How to Use

1. **Hardware Setup:**
   - Connect the 8051 microcontroller, 7-segment displays, LEDs, and other components as per the provided interfacing diagram.
   - Ensure proper power supply and connections.

2. **Software Setup:**
   - Use Keil μVision4 and Proteus VSM for programming and simulation.
   - Load the provided assembly code onto the microcontroller.

3. **Run the Simulation:**
   - Simulate the traffic light controller in Proteus to observe its behavior in different scenarios.

## Results and Conclusion

The system effectively addresses traffic congestion issues and enhances traffic management. The README provides details on the project's results, conclusions, and the benefits of adopting such an intelligent traffic control system.

## Future Scope

The project can be further expanded to include smart traffic light control, congestion avoidance during emergencies, and prioritizing emergency vehicles for smoother traffic flow.


