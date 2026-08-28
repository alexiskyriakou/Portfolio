# Power & Hot-Swap Controller

## Overview

A dual-input power management and monitoring solution designed to
provide controlled power-path management, input prioritization,
hot-swap protection, and real-time electrical monitoring.

The design accepts two independent power inputs and combines them
through an active ideal-diode power path. External N-channel MOSFETs
are controlled by an LTC4227 to provide low-loss power OR-ing,
controlled startup, inrush-current limiting, and overcurrent
protection.

An INA3221 provides high-side voltage and current monitoring of the
power rails through an I2C interface.

## Key Features

- Dual redundant power inputs
- Active ideal-diode power OR-ing
- Input power prioritization
- Hot-swap / controlled power insertion
- Inrush-current limiting
- Overcurrent and short-circuit protection
- External N-channel MOSFET power switches
- High-side current sensing
- Input and output voltage monitoring
- I2C power telemetry
- Programmable warning and critical fault monitoring
- Power-good and fault status outputs
- Reverse-current protection
- Controlled power-path switchover

## System Architecture

The power system consists of two main functional blocks:

1. Power-path and Hot-Swap Controller
2. Voltage and Current Monitoring

### Power Path

Two independent power sources are connected to IN1 and IN2.

The LTC4227 controls external N-channel MOSFETs configured as
ideal-diode elements for each input path. This allows the two inputs
to be combined while minimizing the voltage drop normally associated
with conventional diode OR-ing.

The design also implements input prioritization, allowing one input
source to be selected as the preferred supply while maintaining the
ability to transition to the secondary input when required.

The common power path is subsequently controlled by the Hot-Swap
section of the LTC4227, providing controlled startup and protection
against excessive inrush current and overcurrent conditions.

### Monitoring

The INA3221 monitors the electrical characteristics of the power
system using high-side current sensing.

The monitoring section provides:

- Bus voltage measurement
- Shunt voltage measurement
- Current measurement
- Programmable warning thresholds
- Programmable critical thresholds
- I2C communication

The monitoring data can be read by an external processor or
management controller through the I2C interface.


## Engineering Highlights

- Redundant Power Inputs
The design supports two independent input power sources and
automatically manages the power path between them.

- Ideal-Diode Power OR-ing
External N-channel MOSFETs are used instead of conventional
Schottky diodes to reduce conduction losses and improve power-path
efficiency.

- Input Prioritization
The input control logic provides priority management between the
two power sources, allowing the preferred source to remain active
while providing automatic transition to the secondary source.

- Hot-Swap Protection
The LTC4227 provides controlled MOSFET turn-on to limit inrush
current when the system is connected to a live power source.

- Fault Protection
The design includes overcurrent and fault detection with
FAULT and POWER GOOD status signals.

- Power Monitoring
The INA3221 provides digital monitoring of voltage and current
through an I2C interface, allowing the system controller to
continuously monitor the power system.

## My Contribution

- Power architecture design
- Power-path topology selection
- LTC4227 implementation
- Ideal-diode MOSFET configuration
- Input prioritization circuit
- Hot-swap and inrush-current protection design
- Current-sense implementation
- INA3221 monitoring circuit
- Fault and power-good signal implementation
- Component selection
- Schematic design
- PCB design
- Hardware bring-up and testing
- Electrical debugging and validation
