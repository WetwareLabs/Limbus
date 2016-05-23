# Limbus - Model D

## A low power wireless motion sensor powered by coin cells

### Hardware used:

- Atmega328p
- Panasonic PIR sensor EKMB1101113
- RFM69W wireless module
- SI7021 temperature and humidity sensor
- Watchdog TPL5010
- Flash chip W25X40CL
- CR2450 (soldered in) or CR2032 (battery holder)
- WS2812B RGB led

[Please see the disucssion here.](https://lowpowerlab.com/forum/index.php?topic=1913)


----

### Optional components:

- C2 OR C1 can be omitted (other 10 uF cap is there just in case..)
- Y1 (resonator) can be omitted (works fine with the internal 8 Mhz resonator)
- Flash chip, R6, R15, R5, Q1 can be left out if wireless OTA updates are not wanted
- WS2812B led can be left out or replaced with normal led (with clever usage of existing WS2812B pads :)
- If temperature/humidity sensing is not needed, U2 and C7, R2, R3 can be left out. Also in this case the whole TPL5010 watchdog could be left out since no periodic transmissions are needed (unless you want battery levels transmitted)

-----

## Changelog

Revision 01 files are here only for reference, please use rev 02. 

Note that the updated layout has not yet been tested by me (I have only rev 01 PCBs, where corrections are done with jumper wires), but since modifications are quite minor, I don't anticipate any problems.

Changes in revision 02:

- Removed unnecessary Q2, R9 and R8. Power the WS2812B instead from A1 pin
- Removed unnecessary R14,R13,C6. Read VCC instead measuring 1.1V reference against VCC.
- Swapped through-hole reset switch to SMD one
- Swapped bottom VCC/GND connectors to route GND plane more efficiently (jumper wire or reset switch not necessary)
- PIR output wired to D7 (instead of A7, since it doesn't even have interrupt capability :) 
- Added R11 (100K) between PIR sensor GND and OUT for stability
- Added 100nF cap between PIR sensor GND and VCC (this may not be necessary and is not even in the datasheet, but added just in case..)
- Enlarged holes for CR2450 and partially isolated the GND pin from rest of the ground plane (to make it easier to de/re-solder the battery)
- Routed a connector also from D6 (in addition to D5)
- Other minor layout alterations 


