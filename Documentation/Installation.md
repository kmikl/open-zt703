# Installation

To install the bootloader:
- install STM32CubeProgrammer
- select debugger
- connect
- full chip erase
- select bootloader .hex file from filesystem in the Erasing and Programming menu
- check the options: Verify programming, Run after programming
- hit start programming

On first startup:
- external flash will be erased, and a new filesystem will be created, this takes a while.
- the meter reboots, when finished
- having no firmware installed, SPI flash checksum failed will be displayed
- now the meters internal filesystem will be available over USB
- copy the file OPNZT703.UPD to the UPDATE folder
- when finished press the PWR button, the meter will reboot
- the new firmware will be checked and written to flash
- when finished, the meter will reboot into the new firmware
- the file OPNZT703.UPD can be deleted, no need for it anymore

Updating the firmware:
- copy the new OPNZT703.UPD to the UPDATE folder
- power the meter off
- hold the F3 button, while powering the meter on
- F3 can be released, when the message Verifying update file is displayed
- the new firmware will be checked and written to flash
- when finished, the meter will reboot into the new firmware
- the file OPNZT703.UPD can be deleted, no need for it anymore

Erasing the firmware:
- power the meter off
- hold the F2 button, while powering the meter on
- F2 can be released, when the message Creating filesystem is displayed
- when finished, the meter will reboot
- having no firmware installed, SPI flash checksum failed will be displayed
  

