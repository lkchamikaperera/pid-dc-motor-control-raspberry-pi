# PID-Controlled DC Motor Stabilization System using Raspberry Pi

This project implements a closed-loop DC motor speed control system using a Raspberry Pi, encoder feedback, PWM motor control, and PID control logic. The system was designed to stabilize the speed of a 6V N20 DC motor and maintain a target RPM under real hardware conditions.

## Project Overview

The Raspberry Pi reads motor speed feedback from an optical rotary encoder and compares the measured RPM with the target speed. Based on the error, a PID controller adjusts the PWM signal sent to the TB6612FNG motor driver to regulate the motor speed.

The project includes both hardware and software development, including custom PCB design, encoder-based speed measurement, Python control scripts, PID gain tuning, CSV data logging, graph generation, and performance analysis.

## Key Features

* Closed-loop DC motor speed control
* Raspberry Pi-based PID implementation
* Encoder feedback for real-time RPM measurement
* PWM motor control through TB6612FNG motor driver
* Custom PCB designed using EasyEDA
* Open-loop motor characterization
* Moving average filtering to reduce encoder noise
* Anti-windup protection for PID integral control
* CSV data logging and automatic graph generation
* Disturbance and robustness testing

## Hardware Components

* Raspberry Pi 4
* TB6612FNG motor driver
* 6V N20 DC motor with encoder
* Optical rotary encoder
* Custom PCB
* External motor power supply
* Filtering and protection components

## Software and Tools

* Python
* pigpio
* Matplotlib
* CSV data logging
* EasyEDA
* Raspberry Pi OS

## Source Files

* `main_menu.py` - Menu-driven application for running standard PID tests, custom speed tests, and disturbance tests.
* `final_pid.py` - PID control script with encoder feedback, PWM output, CSV logging, and anti-windup protection.
* `open_loop.py` - Open-loop step response test script for observing motor behavior at fixed PWM duty cycles.
* `live_plot.py` - Live RPM plotting script for real-time motor speed visualization.

## Final Performance

The final tuned PID controller achieved:

* Settling time: 1.82 seconds
* Maximum overshoot: 0.8%
* Steady-state error: 0.0%
* No sustained oscillations

Final PID gains:

```text
Kp = 0.5
Ki = 1.7
Kd = 0.01
```

## Repository Structure

```text
docs/              Project report
hardware/          PCB layout and Gerber fabrication files
src/               Python control and testing scripts
```

## How to Run

Start the pigpio daemon first:

```bash
sudo pigpiod
```

Then run the menu-based application:

```bash
python3 src/main_menu.py
```

## Learning Outcomes

This project strengthened my understanding of feedback control systems, PID tuning, PWM motor control, encoder-based speed measurement, PCB design, hardware testing, and real-time embedded system behavior.

## Project Status

Completed as part of the IE3034 Control System Engineering module.
