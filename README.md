# Arduino Dual-Axis Solar Tracker

This project is an *Arduino-controlled dual-axis solar tracker* designed to improve solar panel efficiency by automatically adjusting its orientation based on sunlight intensity. By utilizing two servo motors and four light-dependent resistors (LDRs), the system continuously aligns the solar panel to face the direction with the most sunlight throughout the day.

# Table of Contents

- Project Overview
- Features
- Hardware Requirements
- Software Requirements
- Circuit Diagram
- How it Works
- Code Explanation
- Future Improvements

# Project Overview

The goal of this project is to create a solar tracker that enhances energy collection from a solar panel by maintaining an optimal angle to the sun. It utilizes two servos to control vertical and horizontal movements of the solar panel based on the light intensity detected by four LDR sensors placed on the panel.

# Features

- *Dual-axis tracking*: Moves both horizontally and vertically to follow the sun.
- *Automatic light detection*: Adjusts based on light intensity readings from LDR sensors.
- *Easy to use*: Requires basic electronic components and an Arduino board.
- *Energy efficient*: Maximizes solar panel exposure to sunlight.

# Hardware Requirements

- Arduino board (e.g., Arduino Uno)
- 2x Servo motors (for horizontal and vertical movement)
- 4x Light-dependent resistors (LDRs)
- 4x 10kΩ resistors (for the LDRs)
- Breadboard and jumper wires
- Solar panel (optional, for demonstration purposes)
- Power supply (5V for servos)

# Software Requirements

- Arduino IDE (to upload the code)
- Servo library (comes pre-installed with the Arduino IDE)

# Circuit Diagram

For this project, you need to connect the LDR sensors in a specific configuration to the analog pins of the Arduino and control the servos through PWM signals. You can refer to the following schematic to set up your hardware.

(*Include or link to a circuit diagram here*)

# How it Works

1. *LDR sensors*: Four LDR sensors are placed at the edges of the solar panel to detect sunlight intensity from different directions.
2. *Servo motors*: Two servo motors adjust the position of the solar panel. One controls horizontal movement, and the other controls vertical movement.
3. *Arduino logic*: The Arduino reads the analog values from the LDR sensors, computes the average light intensity on each side, and adjusts the panel's angle based on the difference in light intensity between the sensors.
4. *Movement control*: If the difference in light intensity exceeds a defined tolerance level, the Arduino sends signals to the servos to adjust the position of the panel.

# Code Explanation

The code for this project reads the values from the four LDRs and adjusts the panel's orientation accordingly.

- The servos are controlled using the `Servo` library.
- Analog pins A0 to A3 are connected to the LDRs to detect light intensity from different directions.
- The program calculates the average light intensity between sensors to determine which direction to move the solar panel.

Here is a brief summary of the main code logic:
- *Vertical adjustment*: If the top sensors detect more light than the bottom sensors, the vertical servo moves the panel up, and vice versa.
- *Horizontal adjustment*: Similarly, if the left sensors detect more light than the right sensors, the horizontal servo rotates the panel in that direction.

For the full code, refer to the `arduino Code` file.

# Future Improvements

Some ideas to enhance this project in the future include:
- Adding *power tracking*: Monitoring the output of the solar panel to ensure it is functioning efficiently.
- *Weather adaptation*: Using sensors to adjust the tracking behavior on cloudy or overcast days.
- *Energy storage*: Integrating a system to store energy in a battery for later use.
