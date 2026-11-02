# Custom STM32F070CB Development Board

## Overview

This project is a custom-designed development board built around the **STM32F070CB** microcontroller. It is intended as a hands-on platform for learning and demonstrating embedded hardware design, from schematic capture and component selection through PCB layout, routing, and design-rule verification.

The board integrates USB connectivity, regulated 3.3 V power, SWD programming/debugging, and headers for commonly used communication interfaces and GPIO. The PCB is designed as a **four-layer board**, with a dedicated inner ground plane and additional copper layers for signal and power routing.

## Key Features

- **Microcontroller:** STM32F070CB in an LQFP-48 package
- **USB interface:** USB connector with ESD protection and USB-C configuration resistors
- **Power:** USB 5 V input and an MCP1826S LDO regulator providing a 3.3 V supply
- **Programming and debugging:** 10-pin ARM SWD connector
- **Communication interfaces:** UART, I²C, and SPI headers
- **General-purpose I/O:** Breakout headers for additional MCU pins
- **User interface:** Reset and user push-buttons, plus an indicator LED
- **Clock:** External 8 MHz crystal with load capacitors
- **PCB stack-up:** Four copper layers, with an inner GND plane

## Hardware Design

### Microcontroller and Power

The STM32F070CB is the central processing unit of the board. Its supply pins are connected to the regulated 3.3 V rail, while its ground pins connect to the common ground network. Local decoupling capacitors are placed near the MCU supply pins to help reduce supply noise and provide transient current.

The board receives 5 V through its USB connector. An MCP1826S low-dropout regulator converts this input to the 3.3 V rail used by the microcontroller and other 3.3 V circuitry. Input and output capacitors support regulator stability and supply filtering.

### USB Interface

The USB interface provides a connection to a host computer. The design includes USB data-line ESD protection and the required USB-C configuration resistors. The USB connector’s ground and shield connections are included in the PCB design.

### Programming and Debugging

A 10-pin ARM SWD header provides access to the microcontroller’s programming and debugging signals, including SWDIO, SWCLK, target voltage reference, ground, and reset. This allows the board to be programmed and debugged using a compatible external debugger.

### Communication and GPIO Expansion

Headers expose the board’s UART, I²C, and SPI signals, along with additional GPIO pins. These interfaces allow external modules, sensors, and test circuits to be connected during firmware development.

The board also includes a user push-button, a reset push-button, and an indicator LED for basic interaction and firmware testing.

### Clock Circuit

An external 8 MHz crystal and its load capacitors provide the MCU’s high-speed external clock source. The crystal circuit is placed close to the microcontroller to keep its connections short.

## PCB Design

The PCB was designed in KiCad using a four-layer stack-up:

| Layer | Intended use |
|---|---|
| F.Cu | Components and primary signal routing |
| In1.Cu | Ground plane |
| In2.Cu | Power routing and additional signals |
| B.Cu | Additional signal routing |

The layout uses copper zones, vias, and routed tracks to connect the components while maintaining separation between different electrical nets. Design-rule checks are used to identify issues such as clearance violations, unconnected items, and other layout errors.

## Design Workflow

The project covers the following hardware-design steps:

1. Define the board’s functional requirements and select components.
2. Create the schematic and assign component footprints.
3. Check schematic electrical rules and verify pin assignments.
4. Transfer the design to the PCB editor and arrange the components.
5. Define the board outline and configure the four-layer stack-up.
6. Route signals and power connections, then add copper zones.
7. Run PCB design-rule checks and review connectivity.
8. Generate a bill of materials (BOM) for component identification and purchasing.

## Repository Contents

The repository is intended to contain the KiCad project files and supporting design outputs, such as:

- Schematic and PCB layout files
- Project configuration and footprint/library references, where applicable
- Bill of materials (BOM)
- Manufacturing outputs, when generated

## Project Status

The schematic and PCB layout have been developed in KiCad, and the design is being checked for electrical connectivity and PCB design-rule compliance. The board should be considered a **development design** until fabrication, assembly, and hardware testing have been completed.

