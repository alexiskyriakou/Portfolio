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
