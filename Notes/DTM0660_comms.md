DTM0660L communication <br />
<br />
Data sent to the DTM0660L chip: 2 bytes at 9600-8-N-1 <br />
- V button: 0x50,0x50 <br />
- mV button: 0x60,0x60 <br /> 
- resistance/diode/continuity/capacitance button: 0x40,0x40 <br />
- 10A button: 0x80,0x80 <br />
- mA button: 0x90,0x90 <br />
- rel (power) button: 0x30,0x30 <br />
- range button: 0x20,0x20 <- cycles through the manual ranges <br />
- range button long push: 0x22,0x22 <- this switches to autorange <br /> 
- hold button: 0x10,0x10 <- this does not do anything apart from beeping and setting the hold bit in byte mode2 <br />
 <br />
Data sent from the DTM0660L chip is basically the segment data: 18 bytes at 9600-8-N-1<br />
- byte 0: 0xFF <br />
- bytes 1 to 5: digits in reverse order <br />
- bytes 6 to 9: 2nd measurement (frequency in AC mode)<br />
- byte 10 mode1 <br />
- byte 11: mode2 <br />
- byte 12 to 14: bargraph<br />
- byte 15: unit1 <br />
- byte 16: unit2 <br />
- byte 17: some kind of checksum, have to figure it out <br />
<br />
Digit decoding: <br />
- 0: 0xEB <br />
- 1: 0x0A <br />
- 2: 0xAD <br />
- 3: 0x8F <br />
- 4: 0x4E <br />
- 5: 0xC7 <br />
- 6: 0xE7 <br />
- 7: 0x8A <br />
- 8: 0xEF <br />
- 9: 0xCF <br />
If bit 4 of the first digit is set, the value is negative <br />
If bit 4 of an other digit is set, the decimal point _before_ the digit is on <br />
<br />
Mode1 decoding: <br />
- 0x02: Hz (2nd. measurement, AC mode) <br />
- 0x03: kHz (2nd. measurement, AC mode) <br />
- 0x20: Relative measurement <br />
- 0x40: Continuity <br />
- 0x80: Diode <br />
<br />
Mode2 decoding: <br />
- if bit 2 is set -> auto range <br />
- if bit 2 is reset -> manual range <br />
- if bit 4 is set -> DC <br />
- if bit 6 is set -> AC <br />
- if bit 7 is set -> Hold active <br />
 <br />
Unit1 decoding (only used with Farad): <br />
- 0x40: n <br />
- 0x80: µ <br />
- 0x0C: m <br />
 <br />
Unit2 decoding: <br />
- 0x01: Ampere <br />
- 0x02: Volt <br />
- 0x04: Farad <br />
- 0x09: mAmpere <br />
- 0x0A: mVolt <br />
- 0x40: Ohm <br />
- 0x50: MOhm <br />
- 0x60: kOhm <br />
<br />
If the digits are 0x00, 0xEB, 0x61, 0x00, 0x10 -> overload
