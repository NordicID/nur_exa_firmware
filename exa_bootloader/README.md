# EXA Bootloader Version History

## VER 16 (23.11.2020)
* Added wathdog functionality

## VER 8  (31.5.2018)
* Fixed main XTAL startup issue at low temperatures.

## VER 7 (14.9.2017)
* Fixed reset source check where it looks now only POWEROFF_RESET flag in order to perform trigger delay.

## VER 6 (25.8.2017)
* Added 500ms delay for trigger button for inorder to prevent accidentally startup's.

## VER 4 (18.5.2017)
* Advertising name is now "DfuEXA"
* New key sequence to enter bootmode manually: poweroff--> press trigger--> press both PAIR and POWER down.
