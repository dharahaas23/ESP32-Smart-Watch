# ESP32 Smart Watch

A round, wrist-worn smart watch built around the ESP32-WROOM-32, with heart-rate sensing, a circular color display, USB-C charging, and a custom PCB antenna — designed as part of the #30DaysOfPCB progression from beginner to advanced boards.

![KiCad](https://img.shields.io/badge/Designed%20in-KiCad%2010-blue) ![Status](https://img.shields.io/badge/status-routed%20%E2%80%94%200%20unrouted-brightgreen)

## Overview

| | |
|---|---|
| **MCU** | ESP32-WROOM-32 |
| **Display** | GC9A01, round TFT (SPI) |
| **Heart-rate sensor** | MAX30102 (I2C) |
| **Charger / protection** | TP4056 + DW01A + FS8205A dual MOSFET |
| **Regulator** | AMS1117-3.3 |
| **USB / programming** | USB-C, CH340K USB-to-TTL bridge |
| **Board shape** | Circular, with a keep-out zone and PCB trace antenna for the ESP32 |
| **Layers** | 4-layer (F.Cu, In1.Cu, In2.Cu, B.Cu) |
| **Pads / Vias / Track segments** | 227 / 78 / 306 |
| **Nets** | 68 (fully routed — 0 unrouted) |

## Features

- **ESP32-WROOM-32** as the main controller, with dedicated `RESET`, `EN`, `BOOT`, and `Button` GPIOs
- **GC9A01 round display** driven over SPI, with separate SDA/SCL/RST/DC/CS lines
- **MAX30102** heart-rate/SpO2 sensor on I2C, footprint placed close to the skin-contact edge for optimal readings
- **USB-C** input for power and CH340K-based UART programming (TXD/RXD/DTR/RTS wired to EN/BOOT for auto-reset)
- **TP4056** single-cell Li-ion charge management with **DW01A + FS8205A** battery protection (over-charge/discharge/current)
- **On/off slide switch** and separate **BOOT** and **Function** push buttons
- **Custom PCB trace antenna** for the ESP32, isolated behind a defined keep-out zone
- Battery connector (BAT+ / BAT−) for a coin/pouch cell


## Design Notes

- Front copper is heavily used for power distribution and the ESP32 antenna keep-out; back copper carries the bulk of signal routing.
- The board silkscreen calls out `PLACE CLOSE TO THE SKIN` next to the MAX30102 footprint as a placement reminder for future revisions/enclosure design.
- Bottom silk includes maker/GitHub branding (`GitHub:dharahaas23`) and a "Designed with KiCad" mark.

## Tools

- **KiCad 10.0.1** — schematic capture, PCB layout, and 3D visualization

## Author

**S. Dharahaas**
GitHub: [@dharahaas23](https://github.com/dharahaas23)
