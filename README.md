# Smart Temperature-Based Fan Controller

An embedded system that automatically adjusts ceiling-fan speed according to
ambient temperature using a microcontroller, temperature/humidity sensor,
servo motor and capacitive fan regulator.

## Project Overview

Traditional ceiling fans require manual speed adjustment even when room
temperature changes significantly.

This project automates the process by continuously monitoring the ambient
temperature and mechanically adjusting the existing fan regulator using a
servo motor.

The system is designed as a low-cost retrofit solution rather than replacing
the existing ceiling fan.

## Key Features

- Real-time temperature monitoring
- Automatic fan-speed adjustment
- Servo-based physical regulator control
- Capacitive fan regulator
- Arduino-based embedded control
- Smooth speed transition
- Manual operation possible
- Low-cost retrofit architecture
- Designed with energy efficiency in mind

## System Architecture

Temperature Sensor
        │
        ▼
   Arduino Uno
        │
        ▼
  Control Algorithm
        │
        ▼
   Servo Motor
        │
        ▼
Capacitive Regulator
        │
        ▼
   Ceiling Fan

## Hardware

| Component | Purpose |
|-----------|---------|
| Arduino Uno | Main controller |
| DHT11/DHT22 | Temperature and humidity sensing |
| Servo Motor | Mechanical regulator control |
| Capacitive Regulator | Fan speed control |
| External Servo Supply | Servo power |
| Ceiling Fan | Controlled appliance |

## Control Logic

| Temperature | Fan Level |
|-------------|-----------|
| < 25°C | Low |
| 25–35°C | Medium |
| 35–45°C | High |
| > 45°C | Maximum |

The servo angle corresponding to each regulator position is calibrated
experimentally.

## Firmware

The firmware is developed using Arduino IDE and the Arduino Servo library.

Main firmware responsibilities:

1. Read temperature and humidity.
2. Determine required fan-speed level.
3. Map fan level to servo position.
4. Move the servo to the calibrated position.
5. Continuously repeat the control process.

## Testing

The prototype was tested by varying the ambient temperature and observing
the corresponding fan speed and servo position.

The project report recorded approximately:

- <25°C → ~200 RPM
- 25–35°C → ~280 RPM
- 35–45°C → ~370 RPM
- >45°C → ~420+ RPM

## Results

The prototype demonstrated automatic fan-speed adjustment based on
temperature.

The servo mechanically rotated the existing regulator, allowing the system
to retrofit an ordinary fan instead of requiring a completely new fan
controller.

## Engineering Challenges

### 1. Servo-Regulator Mechanical Coupling

The servo had to be mechanically aligned with the regulator knob so that
different servo angles corresponded reliably to fan-speed positions.

### 2. Servo Power Supply

The servo uses a separate regulated supply to avoid excessive current
loading on the microcontroller.

### 3. Calibration

The servo angle for each fan-speed level was experimentally determined
using the actual regulator.

### 4. Smooth Control

The firmware was designed to avoid unnecessary abrupt changes in the
regulator position.

## Future Improvements

- Replace threshold control with fuzzy logic/PID control
- Add OLED/LCD monitoring
- Add IoT monitoring
- Add mobile application
- Add power-consumption measurement
- Store temperature and power data
- Design a custom PCB
- Add manual/automatic mode selection
- Add fault detection
- Improve mechanical coupling

## Project Documentation

See the `docs/` directory for:

- Complete project report
- Circuit diagram
- System architecture
- Design notes

## Skills Demonstrated

**Embedded Systems**
- Arduino
- Sensor interfacing
- Servo control
- Embedded C/C++

**Electronics**
- Sensor interfacing
- Motor/servo power supply
- Capacitive fan regulation
- Hardware integration

**Engineering**
- System architecture
- Hardware-software integration
- Calibration
- Experimental testing
- Debugging

## Author

G. B. S. S. Balaji

B.Tech – Electronics and Communication Engineering

GMR Institute of Technology
