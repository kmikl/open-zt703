# Display 
 
Unknown manufacturer
- Only readable text: XX035009SBIO V2
- Size: 3.5"
- Resolution: 320x240
- Pin count: 54
- Backlight current limit: 20mA
- Backlight voltage: around 17V
- Synchronisation: DE-mode only
- DE polarity: active high
- Pixel clock: 20MHz(Stock), fmin is around 5Mhz
 
DE timing:
- Horizontal active 16µs -> 320 pixels
- Horizontal blanking: 9µs -> 180 pixels
- Vertical active: 6ms -> 240 rows
- Vertical blanking: 550µs -> 22 rows
- One full image consist of 131.000 pixel clock cycles
 
Pin connections: 
- 1+2: LED K 
- 3+4: LED A 
- 8: Reset -> MCU pin 7 
- 9-11: SPI -> NC 
- 12-14: B0-B2 -> GND 
- 15-19: B3-B7 -> MCU pins 67,42,25,95,96 
- 20+21: G0+G1 -> GND 
- 22-27: G2-G7 -> MCU pins 15,41,46,47,64,54 
- 28-30: R0-R2 -> GND 
- 30-35: R3-R7 -> MCU pins 34,29,68,35,45 
- 36: HSync -> NC 
- 37: VSync -> NC 
- 38: Pclock -> MCU pin 44 
- 39+40: NC 
- 41+42: Vcc (3V) 
- 43-51: NC 
- 52: DE -> MCU pin 43 
- 53+54: GND 

The display has no auto-refresh, if not given a pixel clock (or the frequency is too low), it cycles through test images (all pixels white, red, green, blue, black).
