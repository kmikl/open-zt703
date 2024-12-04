Display <br />
 <br />
Unknown manufacturer <br />
Only text readable: XX035009SBIO V2 <br />
Size: 3.5" <br />
Resolution: 320x240 <br />
Pin count 54 <br />
Backlight current limit: 20mA <br />
Backlight voltage: around 17V <br />
Synchronisation: DE-mode only <br />
DE polarity: active high <br />
Pixel clock: 20MHz <br />
 <br />
DE timing: <br />
Horizontal active 16µs -> 320 pixels <br />
Horizontal blanking: 9µs -> 180 pixels <br />
Vertical active: 6ms -> 240 rows <br />
Vertical blanking: 550µs -> 22 rows <br />
 <br />
Pin connections: <br />
- 1+2: LED K <br />
- 3+4: LED A <br />
- 8: Reset -> MCU pin 7 <br />
- 9-11: SPI -> NC <br />
- 12-14: B0-B2 -> GND <br />
- 15-19: B3-B7 -> MCU pins 67,42,25,95,96 <br />
- 20+21: G0+G1 -> GND <br />
- 22-27: G2-G7 -> MCU pins 15,41,46,47,64,54 <br />
- 28-30: R0-R2 -> GND <br />
- 30-35: R3-R7 -> MCU pins 34,29,68,35,45 <br />
- 36: HSync -> NC <br />
- 37: VSync -> NC <br />
- 38: Pclok -> MCU pin 44 <br />
- 39+40: NC <br />
- 41+42: Vcc (3V) <br />
- 43-51: NC <br />
- 52: DE -> MCU pin 43 <br />
- 53+54: GND <br />
