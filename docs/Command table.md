## Command table
Sending data from your microcontroller to the blueism firmware needs to follow a fixed packet format, the most important part of which is the command and the data that follows it. The command table describes the commands and their respective data formats.

### UART data packet
All packets are a fixed length of 16 bytes, the packet structure is shown below:

| BYTE   | DESCRIPTION       |
|--------|-------------------|
| Byte0  | Fixed header 0xAA |
| Byte1  | Command           |
| Byte2  | Playload length   |
| Byte3  | Payload data0     |
| Byte4  | Payload data1     |
| Byte5  | Payload data2     |
| Byte6  | Payload data3     |
| Byte7  | Payload data4     |
| Byte8  | Payload data5     |
| Byte9  | Payload data6     |
| Byte10 | Payload data7     |
| Byte11 | Payload data8     |
| Byte12 | Payload data9     |
| Byte13 | Payload data10    |
| Byte14 | Checksum          |
| Byte15 | Fixed char '\n'   |

The Byte2 is the actual payload length that the packet contains, if the packet does not contain any payload, then this btye is 0.

Checksum calculation:

((Byte0+Byte1+Byte2+...Byte12+Byte13)-0x55)&(0xFF)

### Commands

#### Reserved Field

This Field is reserved for further use.

#### Bluetooth Field

**0x10**: reserved

**0x11**: Bluetooth unpair command

| BYTE         | DESCRIPTION       |
|--------------|-------------------|
| Byte0        | Fixed header 0xAA |
| Byte1        | 0x11              |
| Byte2        | 0x00              |
| Byte3~Byte13 | 0x00              |
| Byte14       | Checksum          |
| Byte15       | Fixed char '\n'   |

**0x12**: reserved

**0x13**: reserved

**0x14**: reserved

**0x15**: reserved

**0x16**: Bluetooth battery update command

| BYTE         | DESCRIPTION       |
|--------------|-------------------|
| Byte0        | Fixed header 0xAA |
| Byte1        | 0x16              |
| Byte2        | 0x01              |
| Byte3        | Battery level     |
| Byte4~Byte13 | 0x00              |
| Byte14       | Checksum          |
| Byte15       | Fixed char '\n'   |

#### HID Report Field

**0x20**: reserved

**0x21**: HID keyboard report command

| BYTE          | DESCRIPTION       |
|---------------|-------------------|
| Byte0         | Fixed header 0xAA |
| Byte1         | 0x21              |
| Byte2         | 0x07              |
| Byte3         | mods              |
| Byte4         | key0              |
| Byte5         | key1              |
| Byte6         | key2              |
| Byte7         | key3              |
| Byte8         | key4              |
| Byte9         | key5              |
| Byte10~Byte13 | 0x00              |
| Byte14        | Checksum          |
| Byte15        | Fixed char '\n'   |

**0x22**: HID mouse report command

| BYTE         | DESCRIPTION       |
|--------------|-------------------|
| Byte0        | Fixed header 0xAA |
| Byte1        | 0x22              |
| Byte2        | 0x05              |
| Byte3        | mouse buttons     |
| Byte4        | mouse x           |
| Byte5        | mouse y           |
| Byte6        | mouse wheel v     |
| Byte7        | mouse wheel h     |
| Byte8~Byte13 | 0x00              |
| Byte14       | Checksum          |
| Byte15       | Fixed char '\n'   |

**0x23**: HID consumer report command

| BYTE         | DESCRIPTION       |
|--------------|-------------------|
| Byte0        | Fixed header 0xAA |
| Byte1        | 0x23              |
| Byte2        | 0x02              |
| Byte3        | usage_h           |
| Byte4        | usage_l           |
| Byte5~Byte13 | 0x00              |
| Byte14       | Checksum          |
| Byte15       | Fixed char '\n'   |

**0x25**: reserved

**0x26**: reserved

#### System control Field

This Field is reserved for further use.