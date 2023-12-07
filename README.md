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

The assembly code for the 8051 microcontroller is provided in the `Keil.asm` section of this repository. It includes the logic for controlling the traffic lights and countdown timer based on specific conditions.
       
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


