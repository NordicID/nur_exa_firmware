# EXA Application Version History

## VER 2.1.2 (25.8.2017)

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

## VER 2.0.9 (13.6.2017)

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

