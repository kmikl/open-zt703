# Serial communication

The firmware support remote control and monitoring over a USB-CDC connection

Data sent from the meter to the PC:</br>
(Measured value) (Unit) (2nd. Value) (Mode) (Logging) </br>
Example: 205.23mVAC 51.94 Hz A L

Measured value: main measured value</br>

Unit: self explanatory</br>

2nd. value: frequency, only sent in AC mode</br>

Mode:
- A : autorange
- H : hold active, the measured values are still sent over USB, only the screen is frozen
- R : relative measurement activated
- C : continuity mode
- D : diode mode
- L : logging activated (all keys, except PWR/REL and HOLD/SAVE) are deactivated

Commands, that can be sent from the PC to the meter
- 1: button F1
- 2: button F2
- 3: button F3
- 4: button F4
- 5: button PWR/REL short press
- 6: button AUTO/RANGE short press
- 7: button HOLD/SAVE short press
- 8: button AUTO/RANGE long press
- 9: button HOLD/SAVE long press
- 0: button MODE short press
- enter : button MENU
- left : button LEFT
- right : button RIGHT
- up : button UP
- down: button DOWN
