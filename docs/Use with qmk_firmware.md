## Use with qmk_firmware

With nrfpill and blueism firmware, it is possible to make a bluetooth keyboard using QMK firmware.

[Onekey example](https://github.com/luantty2/qmk_firmware/tree/qmk_master_build_2023q2/keyboards/onekey_nrfpill)

### Testing
To test bluetooth function of onekey example on your nrfpill, complete the following steps:

1. Flash XIAO with blueism firmware.
2. Flash Blackpill with onekey example.
3. Power on your nrfpill from a battery, alternatively, you can power it from the USB port of XIAO. You should avoid powering it from the USB port of Blackpill, or the data will be sent over USB rather than Bluetooth. 
4. On your computer or smart phone, search for Bluetooth devices and connect to the device named "Blueism". The RGB LED on XIAO turns into green once connected.
5. Open a text editor and repeatedly press the user button(A0) on the Blackpill, observe that letter "A" is received by your host.
6. The example also demonstrates battery report, this is done by simulating battery level from 100 to 0, the implementation can be found in keymap.c.

