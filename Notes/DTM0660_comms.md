# DTM0660L communication 

Data sent to the DTM0660L chip: 2 bytes at 9600-8-N-1 
- V button: 0x50,0x50 
- mV button: 0x60,0x60  
- resistance/diode/continuity/capacitance button: 0x40,0x40 
- 10A button: 0x80,0x80 
- mA button: 0x90,0x90 
- rel (power) button: 0x30,0x30 
- range button: 0x20,0x20 <- cycles through the manual ranges 
- range button long push: 0x22,0x22 <- this switches to autorange  
- hold button: 0x10,0x10 <- this does not do anything apart from beeping and setting the hold bit in byte mode2 
 
Data sent from the DTM0660L chip is basically the segment data: 18 bytes at 9600-8-N-1
- byte 0: 0xFF 
- bytes 1 to 5: digits in reverse order 
- bytes 6 to 9: 2nd measurement (frequency in AC mode)
- byte 10 mode1 
- byte 11: mode2 
- byte 12 to 14: bargraph
- byte 15: unit1 
- byte 16: unit2 
- byte 17: some kind of checksum, have to figure it out 

Digit decoding: 
- 0: 0xEB 
- 1: 0x0A 
- 2: 0xAD 
- 3: 0x8F 
- 4: 0x4E 
- 5: 0xC7 
- 6: 0xE7 
- 7: 0x8A 
- 8: 0xEF 
- 9: 0xCF 
If bit 4 of the first digit is set, the value is negative 
If bit 4 of an other digit is set, the decimal point _before_ the digit is on 

Mode1 decoding: 
- 0x02: Hz (2nd. measurement, AC mode) 
- 0x03: kHz (2nd. measurement, AC mode) 
- 0x20: Relative measurement 
- 0x40: Continuity 
- 0x80: Diode 

Mode2 decoding: 
- if bit 2 is set -> auto range 
- if bit 2 is reset -> manual range 
- if bit 4 is set -> DC 
- if bit 6 is set -> AC 
- if bit 7 is set -> Hold active 
 
Unit1 decoding (only used with Farad): 
- 0x40: n 
- 0x80: µ 
- 0x0C: m 
 
Unit2 decoding: 
- 0x01: Ampere 
- 0x02: Volt 
- 0x04: Farad 
- 0x09: mAmpere 
- 0x0A: mVolt 
- 0x40: Ohm 
- 0x50: MOhm 
- 0x60: kOhm 

If the digits are 0x00, 0xEB, 0x61, 0x00, 0x10 -> overload
