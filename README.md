# AT89s51-dev-board
A modern AT89S52 (8051) development board featuring USB Type-C power, CH340C USB-to-UART, ISP programming, and a complete open-source hardware design documented from schematic to PCB.
---

## Overview

This project aims to build a modern development board around the **AT89S52** microcontroller with features commonly found in commercial development boards while keeping the design simple, educational, and open-source.

Unlike many existing AT89S52 boards, this design integrates **USB Type-C power**, **USB-to-UART communication**, and **ISP programming support**, making it more convenient for modern development.

---

## Features

- AT89S51 (8051 Architecture)
- USB Type-C Power Input
- CH340C USB-to-UART Converter
- Automatic Power Source Selection
- External Power Input
- ISP Programming Header
- 11.0592 MHz Crystal Oscillator
- Hardware Reset Circuit
- Power LED
- GPIO Expansion Headers
- 5V Logic

---

## Block Diagram

```text
                    +--------------------+
                    |     USB Type-C     |
                    +---------+----------+
                              |
                    +---------v----------+
                    | Power Protection   |
                    | & Auto Selection   |
                    +---------+----------+
                              |
                            +5V Rail
                              |
      +-----------------------+-----------------------+
      |                                               |
+-----v------+                               +--------v--------+
|   CH340C   |                               |    AT89S52      |
| USB-UART   |<-------- UART --------------->| 8051 MCU        |
+------------+                               +--------+--------+
                                                      |
                                        +-------------+-------------+
                                        |                           |
                                   ISP Header                 GPIO Headers
```

---

## Power Architecture

The board supports two power sources:

- USB Type-C (5V)
- External 5V Supply

Automatic source selection is implemented using Schottky diode OR-ing to prevent reverse current between the two supplies.

---

## USB Interface

The onboard CH340C provides:

- USB-to-UART communication
- Serial debugging
- Terminal communication

> **Note:** The CH340C cannot program the AT89S52. Programming is performed through the ISP header.

---

## Programming

Programming is performed using an external ISP programmer.

Supported programmers include:

- USBasp
- AT89 ISP Programmer
- Compatible 8051 ISP programmers

---

## Planned Features

- [ ] USB ESD Protection
- [ ] Resettable Polyfuse
- [ ] User LEDs
- [ ] Push Buttons
- [ ] LCD Header
- [ ] Buzzer
- [ ] Servo Header
- [ ] 3.3V Output
- [ ] Test Points
- [ ] Silkscreen Labels

---

## Design Tools

- KiCad
- Proteus (Firmware Testing)
- Keil µVision (Firmware Development)

---

## Objectives

This project is being developed to:

- Practice professional PCB design
- Learn USB Type-C implementation
- Understand power management techniques
- Design reliable embedded hardware
- Create an open-source AT89S51 development platform

---

## Future Improvements

- Native USB Programmer
- On-board Bootloader
- SWD/JTAG Debug Interface (for future MCU variants)
- Modular Expansion System
- Integrated Logic Analyzer Header
---

## Author

**Shravan Mathapati**

---

## Contributing

Suggestions, improvements, and pull requests are always welcome.

If you find any issues with the schematic or PCB, feel free to open an issue or submit a pull request.

---

⭐ If you find this project useful, consider giving it a star!
