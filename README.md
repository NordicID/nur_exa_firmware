## EXA device firmware
This repository contains stable releases of EXA device firmware.

## Updating instructions
Use the RFIDDemo application for updating device (EXA) or RFID module (NUR) firmware.

Inorder to gain maximum RFID reading data through put, it's recommended to use **"exa_application_xxx-H**" (high speed) version with mobile phones / tablets equipped with Bluetooth version 4.2 or higher.
Use "**exa_application_xxx-L**" in applications where high data through put requirement is not critical or mobile phone doesn't work properly with -H version.
## Version history

### VER 2.4.4-H (23.11.2020)
- Fix missing trig down event while reading barcode
- Added vibration in HID mode for indicating successful read.
- Fixed hang issue while operating in HID mode.
- Added watchdog functionality
- Added delay for charging start

### VER 2.3.4	(3.10.2019)
- Fixed: SetBLEName ext command is now AccEnumSensor causing name corrupted
- Auto repair if BLE name corrupted

### VER 2.3.2 (29.5.2019)
- Added possibility to clear pairing list while connected by keeping button Unpair + Power key down at least 2 second.
- Fixed pairing icon appearing on android in to generic (formaly gamepad) if HID mode not enabled when using paired connection.

### VER 2.2.9 (9.5.2019)
* Fixed barcode scan activate bug when using accessory command readBarcodeAsync without aiming preceeded.

### VER 2.2.8 (17.1.2019)
* Increased NUR2 power-up fail timeout from 5 sec to 10 sec.
* Decreased "No connection timeout" from 6 min to 90 sec.
* NUR Module is powered all the time after boot for EXA51e. Idle timer (5min) still pending.

### VER 2.2.7 (4.9.2018)
* Check battery state before powerup. If battery too low for powerup, device run on charging loop until enough power for starting.
* Wireless charge off on BLE disonnect & power off.

### VER 2.2.5 (31.5.2018)
* Added device type information in to advertising (manufacturer) data. LSB 0x31=EXA31 0x51=EXA51 0xFF=No Config.
* Fixed main XTAL startup issue at low temperatures.

### VER 2.2.4 (18.4.2018)
* Fixed HID service lost issue after 4th or 5th connection with peer.

### VER 2.2.3 (19.3.2018)
* HID fixes (Works also on MacBook)
* Unpairing fixes. (Device restart now after unpairing button pressed)

### VER 2.2.2 (17.1.2018)

* Increased "Longwrite" buffer from 256 --> 1024. (Required when updating NUR FW via PC BLE)
* Added possibility to Enable/disable pairing with peer device. By default pairing disabled.
* Fixed Flash storage operation issue when reading configuration barcode.

### VER 2.2.0 (27.11.2017)

* Improved EXA31 connectivity.
* Prevented automatic restart when EXA51 is on table charger and battery is full.
* Fixed Nur comm bug after imagerConfig. Serial route did not changed after imagerConfig command.
* Added 15ms delay between chars when sending using HID mode. (works better with IOS devices)
* Fixed starup bug when charger plugged in.
* Fixed high current charging bug
* Fixed "long write" bug. Causes device reset when need to write long EPC code. Works now on IOS.

### VER 2.1.3 (14.9.2017)

* Changed Max connection interval from 60ms to 15ms when using MTU 23 ("default") version.
* Two version of FW supported "default -L" (Mtu=23) "High speed -H" (Mtu=158). High speed version recommended to devices communicating with BLE 4.2 or higher.

### VER 2.1.2 (25.8.2017)

* Fixes for temperature control when charging. Charging off if temp rises > 45 celsius.
* Imager powerup and standby when BLE connection. Provides fast scanning start.
* Increased maximum BLE connection interval from 30ms to 60ms. Helps to connect and maintain connection at IOS devices without need for pairing.
* Added possibility to power down device while active BLE connection by keeping power button down at least 7 seconds.
* NUR idle timeout = 30 sec. NUR2 idle timeout = 5min
* Fixed BLE led blink during barcode reading
* Fixed barcode reader aiming flash just before entering to sleep.
* Fixed barcode scan stop when connection to application pending and user press trigger for canceling scan. (it is host app job to do cancelling)
* Added 25ms delay after sending linefeed char (RFID HID mode) (mainly fix for IOS devices preventing linefeed problems)
* Fixed Imager ACK response reading bug. Prevents lost of characters when reading 1D-codes.
* Fixed delay when rising from low power mode.

### VER 2.0.9 (13.6.2017)

* Prevented unexpected restart when power off.
* Making sure vibra and leds are not staying on when power off.
* Buttons disabled during boot phase. Enabled when blue led start blinking.
* RFID on led off during boot phase.
* Reading strange config barcode emits low double beep. (Same as in HID mode if tags not found)
* Scanning config code can be aborted by pressing trigger button again.
* No need to reset device anymore after scanning HID mode config barcode. 
* Blue led off while scanning config barcode.
* Pressing UNPAIR button (3 sec) emit triple beeps and reset only if there was existing pairing information)
* New BLE extension for querying latest MTU and DLE information. (BLE_EXT_GET_CONNECTION_INFO 18) return string.
