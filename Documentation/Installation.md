# Installation

## To install the bootloader:
- install STM32CubeProgrammer
- connect an STM32CubeProgrammer compatible SWD capable debugger (ST-Link, Segger J-Link) to the meters debug port: TMS->SWDIO, TCK->SWCLK, VIN-> do not connect, GND->GND 
- **WARNING**: the meter uses 3V power internally! When connecting a debugger without an output buffer (like most cheap ST-Link V2 clones), that is using 3.3V, the MCU could be damaged. It is recommended to put either series resistors (say 1k) betwen the meter and the debugger communication lines, or take the risk and be quick with the next steps and disconnect the debugger from USB as soon as possible.
- select the used debugger
- connect
- execute Full chip erase
- select bootloader .hex file from filesystem in the Erasing and Programming menu
- turn on the options (if not turned on already): Verify programming, Run after programming
- hit start programming
- press disconnect

## On first startup:
- the external flash will be erased, and a new filesystem will be created, this takes a while
- the meter reboots, when finished
- having no firmware installed, SPI flash checksum failed will be displayed
- now the meters internal filesystem will be available over USB
- copy the file OPNZT703.UPD into the UPDATE folder
- when finished press the PWR button, the meter will reboot
- the new firmware will be checked and written to flash
- when finished, the meter will reboot into the new firmware
- the file OPNZT703.UPD can be deleted, no need for it anymore

## Updating the firmware:
- copy the new OPNZT703.UPD to the UPDATE folder
- power the meter off
- hold the F3 button, while powering the meter on
- F3 can be released, when the message Verifying update file is displayed
- the new firmware will be checked and written to flash
- when finished, the meter will reboot into the new firmware
- the file OPNZT703.UPD can be deleted, no need for it anymore

## Erasing the firmware:
This will also reformat the filesystem and reset all settings to the default values
- power the meter off
- hold the F2 button, while powering the meter on
- F2 can be released, when the message Creating filesystem is displayed
- when finished, the meter will reboot
- having no firmware installed, SPI flash checksum failed will be displayed
- now the meters internal filesystem will be available over USB
