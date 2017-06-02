== EXA Application ==

Version History:
---------------------------------------------------------------
2.0.8 2.6.2017
Fixes: EXA51 Led functionality when powering up from power button.
-Pressing power button >> Right led RED on.
-Keeping power button down at least 1200ms >> Right led turns GREEN ?device starting.
-Releasing power button before 1200ms >> device back to sleep.

-Added delay after connect before request new MTU from phone.
-Fixes for deleting pairing list. Making reset before deletion done  causes unpredictable behavior and probably cause of PM_UNEXPECTED_ERROR seen.
-Fixes for producing beep sounds. Occasionally device hangs to produces constant sound until key pressed.
 
Changes for HID modes:

Functionality (Johannes style) when both: HID Barcode & HID RFID are enabled.

1.	TRIGGER click (short press (<350ms) and released immediately) >> Barcode scanning start immediately without aiming.
2.	TRIGGER press and keeping down at least 350ms >> Imager aimer on >> TRIGGER released >> Barcode scanning starts.
3.	TRIGGER “double click” and keeping down >> RFID scanning start. Searching tags. Beep when tags found. >> TRIGGER released >> If tags found, sending tags to HID. Short beep/tag. If tags not found, double low beeps.
4.	TRIGGER press during tag send >> Tag sending aborted.
5.	TRIGGER press during barcode scanning >> Barcode scanning aborted.
