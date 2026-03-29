# Dual Axis Solar Tracker using Arduino

This project is an **automatic dual-axis solar tracking system** built using an Arduino, four LDR sensors, and two servo motors. It continuously adjusts the position of the solar panel to maximize sunlight exposure.

## Project Overview

The system detects light intensity from four directions using LDRs and moves the solar panel:
- **Horizontally** using one servo motor.
- **Vertically** using another servo motor.

By comparing the light levels from the sensors, the Arduino decides the direction in which the panel should move.

## Features

- Dual-axis tracking: horizontal and vertical movement.
- Uses four LDR sensors to detect sunlight direction.
- Automatically aligns the solar panel toward the brightest light source.
- Simple and low-cost hardware implementation.
- Suitable for small solar panel prototypes and educational demonstrations.

## Components Required

- Arduino board
- 2 × Servo motors
- 4 × LDR sensors
- 4 × resistors
- Breadboard
- Jumper wires
- Solar panel or panel model
- Power supply

## Circuit Connections

### LDR Connections
- Top Left LDR → `A0`
- Top Right LDR → `A3`
- Bottom Left LDR → `A1`
- Bottom Right LDR → `A2`

### Servo Connections
- Horizontal servo signal pin → `D2`
- Vertical servo signal pin → `D13`

## Working Principle

The code reads the analog values from all four LDRs and calculates:
- Average of top sensors
- Average of bottom sensors
- Average of left sensors
- Average of right sensors

Then it compares:
- Top vs bottom light difference for vertical movement.
- Left vs right light difference for horizontal movement.

If the difference is greater than the tolerance value, the Arduino slightly moves the corresponding servo motor toward the brighter side.

## Code Logic

- Read all four LDR values.
- Calculate average light values.
- Find vertical and horizontal differences.
- Move the vertical servo if top and bottom light levels differ significantly.
- Move the horizontal servo if left and right light levels differ significantly.
- Repeat continuously with a small delay.

## Software Used

- Arduino IDE

## Libraries Used

- `Servo.h`

## How to Run

1. Connect all components according to the pin mapping.
2. Upload the Arduino sketch to the board.
3. Power the circuit.
4. Place the LDRs in the correct orientation.
5. Observe the servo motors adjusting the panel toward the brightest light.

## Applications

- Solar energy optimization
- Smart solar panel systems
- Educational robotics projects
- Embedded systems demonstrations

## Limitations

- Accuracy depends on LDR placement and ambient light conditions.
- Servo movement may be slow for rapid sunlight changes.
- Requires proper calibration for best results.

## Future Improvements

- Add LCD display for real-time sensor readings.
- Use a real solar panel with battery charging circuit.
- Add Wi-Fi or IoT monitoring.
- Improve tracking accuracy using PID control.

## License

This project can be used for educational purposes. Add a license as needed before publishing to GitHub.
