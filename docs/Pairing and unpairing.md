## Pairing and unpairing

### Pairing
Blueism can be paired with any host that supports Bluetooth LE 5.0/4.2, Bluetooth BR / EDR hosts are not supported. Please note that the pairing method will vary depending on your host.

* To start pairing, you must power up the XIAO, and XIAO will automatically start bluetooth advertising after powering up.

* When bluetooth is advertising, the RGB LED on the XIAO will turn blue, start bluetooth searching on your computer or phone, a device named "Blueism" is expected to appear in the search list.

* Click the "Blueism" device in the search list to establish a connection between the host and XIAO, if the RGB LED on the XIAO turns green, it means the connection has been successful. 

The blueism firmware can only remember one host at the moment, you have to unpair the formor host before you can pair with the second one.

### Unpairing

* According to the command table, sending unpair command to make blueism firmware forget the current host. The blueism firmware will restart advertising after unpairing.

Please note that terminating a connection from host does not equal to unpairing, the id key of the host is still stored in the flash memory of XIAO.