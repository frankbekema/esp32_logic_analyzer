# ESP32 Logic Analyzer

This repository contains an experimental logic analyzer application for ESP32 series chips. It is based on [ok-home/logic_analyzer](https://github.com/ok-home/logic_analyzer) and aims to improve compatibility with Sigrok's PulseView.

The firmware samples up to eight digital channels using the I2S peripheral and streams captured data over a serial connection via the SUMP protocol. PulseView can connect directly to the device to display the waveforms. Optional CLI and WebSocket interfaces are also available.

## Features

- Up to eight channels captured via I2S
- Configurable sampling clock and trigger conditions
- SUMP protocol support for PulseView
- Optional command line or WebSocket interfaces
- Separate or in-application operation modes

## Building

1. Install the [ESP-IDF](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/).
2. Configure the project:
   ```bash
   idf.py menuconfig
   ```
   Select the **Logic Analyzer** menu to enable SUMP or CLI modes and assign GPIOs.
3. Build and flash:
   ```bash
   idf.py -p PORT flash monitor
   ```

## Using PulseView

When SUMP mode is enabled, open PulseView and choose the **SUMP logic analyzer** driver. Select the serial port of your board and the baud rate configured in `menuconfig` (by default 921600 baud) to start capturing.

## License

Unless otherwise noted in a source file, the code in this repository is released into the public domain (CC0).
