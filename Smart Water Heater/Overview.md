# ESP32-S2 Smart Relay & Sensor Controller
## Overview

A smart IoT controller and power management solution designed to provide reliable dual-relay switching, sensor data acquisition, local user control, and Wi-Fi connectivity.

The design accepts AC mains power, which is stepped down via an HLK-5M05 AC-DC module to provide 5V, and further regulated down to 3.3V via a BL1117-33CX LDO to power the logic components.

An ESP32-S2-Mini-1 module handles system control and wireless communication. Dual electromechanical relays (RF-SS-105DM) are driven by 2N7002-7-F MOSFETs with optocoupler isolation (ORPC-817S/B) to safely manage external loads.
Key Features

- ESP32-S2-Mini-1 microcontroller with Wi-Fi
- AC-DC power conversion (HLK-5M05) providing 5V output
- 3.3V voltage regulation (BL1117-33CX LDO)
- Dual electromechanical relay outputs (RF-SS-105DM)
- MOSFET relay drivers (2N7002-7-F) with flyback diodes (1N4148WSG)
- Optocoupler isolation (ORPC-817S/B) for relay control protection
- Integrated RGB status indicator LED (E6C0606RGBC3UDA)
- Tactile push buttons for manual control, factory reset, and programming
- Temperature sensor interfaces via dedicated headers
- SPI and GPIO expansion headers (CS, MOSI, CLK, MISO)
- Dedicated programming port with auto-reset circuit using L8050HQLT1G transistors
- Standard JTAG debugging interface

## System Architecture

The hardware system consists of three main functional blocks:

- Power Supply and Regulation
- Processing and User Interface
- Switching, Sensing, and Communications

## Power Supply and Regulation

AC mains voltage is supplied to the board and converted via the HLK-5M05 module to produce a stable 5V rail.

A BL1117-33CX low-dropout regulator steps the 5V rail down to 3.3V to power the ESP32-S2 module and peripheral logic. Decoupling capacitors are placed across power rails to ensure noise filtering and voltage stability.
Processing and User Interface

The ESP32-S2-Mini-1 acts as the central processing unit, managing Wi-Fi connectivity and application logic.

User interaction and status feedback are supported by an RGB LED for visual status indication and push buttons for manual operations, such as factory resets or entering programming mode. A dedicated programming header with transistor-based auto-reset circuitry facilitates firmware flashing.
Switching, Sensing, and Communications

Two independent relay circuits allow the system to switch high-voltage or high-current loads. Each relay is driven by a 2N7002 MOSFET, with ORPC-817 optocouplers providing galvanic isolation between the low-voltage logic and the relay coils, alongside 1N4148 flyback diodes to suppress voltage spikes.

External sensor headers allow temperature monitoring, while expansion headers break out SPI lines (MOSI, MISO, CLK, CS) and additional general-purpose I/O for system expansion.
Engineering Highlights

- Isolated Relay Driving
    The design uses optocouplers to isolate the low-voltage microcontroller pins from the electromechanical relay coils, protecting the logic circuitry from inductive kickback.
- Integrated AC-DC Conversion
    Features an onboard HLK-5M05 power module, allowing the board to run directly from AC mains power without requiring an external wall adapter.
- Automated Programming Circuitry
    Incorporates transistor-based auto-reset logic connected to the programming port to streamline firmware updates without manual button timing.
- Flexible Peripherals
    Provides multi-pin headers for SPI communication, temperature sensors, and debugging, making the hardware adaptable for various IoT monitoring and automation tasks.

## My Contribution

- Hardware architecture and system design
- Power supply and regulation circuit implementation (HLK-5M05 and BL1117)
- ESP32-S2 integration and peripheral mapping
- Dual-relay driver design with MOSFETs and optocoupler isolation
- Sensor interface and expansion header layout
- Programming port and auto-reset circuit design
- Component selection and schematic capture
- PCB layout, routing, and design rule validation
- Hardware bring-up, debugging, and testing
