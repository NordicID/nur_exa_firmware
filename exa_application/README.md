# EXA Application Version History

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

