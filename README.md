pyODB
=====

Fork from http://www.obdtester.com/pyobd, a OBD-II compliant car diagnostic tool.

pyOBD (aka pyOBD-II or pyOBD2) is an OBD-II compliant car diagnostic tool. It is designed to interface with low-cost ELM 32x OBD-II diagnostic interfaces such as ELM-USB. It will basically allow you to talk to your car's ECU,... display fault codes, display measured values, read status tests, etc. All cars made since 1996 (in the US) or 2001 (in the EU) must be OBD-II compliant, i.e. they should work with pyOBD.

pyOBD is written entirely in Python and was originally written by Donour Sizemore, now maintained and improved by SECONS Ltd. and forked here.  It is Free Software and is distributed under the terms of the GPL.

### General OBD-II information
Connect to a vehicle	Display tests status	View live sensor data	Read and clear fault codes
For Python devlopers, pyOBD provides a single module, obd_io, that allows high level control over sensor data and diagnostic trouble code managment.

### Requirements
An ELM 32x OBD-II interface
Python 2.x or greater
pySerial
A car supporting OBD-II

### Quick Start Ubuntu
```bash
sudo usermod -a -G dialout [your_user_name]
sudo apt-get install python-wxgtk2.8
git clone https://github.com/chethenry/pyODB
cd pyODB
./pyODB
```

### Hacking Guide
You can communicate directy with you ELM over screen.
```bash
screen /dev/ttyACM0 38400
```
Then use commands given from:
https://www.sparkfun.com/datasheets/Widgets/ELM327_AT_Commands.pdf

### Additions In This Fork
* Ability to query all realtime sensor messages and decode most given the formulas from: http://en.wikipedia.org/wiki/OBD-II_PIDs
* Remove sensors from list that are not supported by the connected auto.

### TODO
* Obtain a more complient ELM32x reader that can forward CAN messages: https://www.sparkfun.com/products/9555
* Add a CAN messages tab that will display raw messages
* Add decoding for known CAN messages
* Add hooks to the sensor tab for related CAN messages

