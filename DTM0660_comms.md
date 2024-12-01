This is a work in progress file, basically a notepad <br />
 <br />
Data sent to the DTM0660L chip: 2 bytes at 9600-8-N-1 <br />
<br />
- voltage button: 0x50,0x50 <br />
- resistance/diode/continuity/capacitance button: 0x40,0x40 <br />
- 10A current button: 0x80,0x80 <br />
- mA current button: 0x90,0x90 <br />
- range button: 0x20,0x20 <br />
- range button long push: 0x22,0x22 <br />
- hold button: 0x10,0x10 <br />
 <br />
Data sent from the DTM0660L chip: 18 bytes at 9600-8-N-1<br />
 <br />
- byte 0: 0xFF <br />
- bytes 1 to 5: digits in reverse order <br />
- byte 11 mode2 <br />
- byte 12: mode <br />
- byte 16: unit <br />
- byte 17: checksum + 4 <br />
 <br />
Digit decoding: <br />
 <br />
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
If bit 7 is set, the decimal point _before_ the digit is on <br />
 <br />
Mode2 decoding: <br />
 <br />
- 0x40: Continuity <br />
- 0x80: Diode <br />
 <br />
Mode decoding: <br />
 <br />
- 0x00: Resistance manual range <br />
- 0x04: Resistance auto range <br />
- 0x10: DC manual range <br />
- 0x14: DC auto range <br />
- 0x40: AC manual range <br />
- 0x44: AC auto range <br />
 <br />
Unit decoding: <br />
 <br />
- 0x01: A <br />
- 0x02: V <br />
- 0x04: nF <br />
- 0x09: mA <br />
- 0x40: Ohm <br />
- 0x50: MOhm <br />
- 0x60: kOhm <br />
