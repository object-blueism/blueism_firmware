# Blueism firmware
## Overview
The blueism is a firmware created for Seeed Studio XIAO nrf52840, which is a tiny board with a bluetooth 5.0 microcontoller. The blueism firmware enables XIAO to receive commands and data from other microcontrollers, then it send those data to HID host via bluetooth. It is suitable for converting devices that do not support wireless functionality into wireless devices.

All testing has been done on the [nrfpill](https://github.com/object-blueism/nrfpill) and is untested on other custom hardware.

Blueism firmware is developed with nrf connect sdk, the source code for the firmware is not publicly available due to potential licensing issues. Please note that the whole project is under testing and updating and should not be used in demanding applications.

## Features

| Implmented feature     | Status  |
|------------------------|---------|
| BT HID keyboard report | Testing |
| BT HID LEDs            | Testing |
| BT HID mouse report    | Testing |
| BT HID consumer report | Testing |
| Battery report         | Testing |


| Planned feature               |
|-------------------------------|
| BT HID keyboard report (NKRO) |
| BT HID system report          |
| BT MIDI                       |

## Documention
* [nrfpill](https://github.com/object-blueism/nrfpill)
* [Flashing](https://github.com/object-blueism/blueism_firmware/blob/main/docs/flashing.md)
* Pairing and unpairing
* Command table
* Use with qmk_firmware