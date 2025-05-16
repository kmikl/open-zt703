# DMM Mode

## Status bar description:
- **AVG** : averaging active
- **USB** : USB connection active
- **AUTO** : autorange active
- **REL** : relative measurement active
- **HOLD** : measured value frozen
- **LIM** : limits active
- **LOG** : logging to flash

## General usage
- **F1 button** : switch between Volts and milliVolts
- **F2 button** : switch between Amps and milliAmps
- **F3 button** : switch between resistance, continutiy, diode and capacitance modes
- **F4 button** : switch between DC and AC modes (only works in Volts/milliVolt and Amps/milliAmps modes)
- **PWR/REL button** : short press turns relative measusement on/off, long press turns the meter on/off
- **AUTO/RANGE button** : short press cycles between manual ranges, long press switches to autorange
- **HOLD/SAVE button** : short press freezes the measured value (hold mode), long press will depending on the setting, save a screenshot and/or turns logging mode on/off
- **MODE button** : ~~switches between DMM and oscilloscope modes~~ at the current state of the firmware, this button has no function

## Limit mode
Limits can be set for each measuring mode independently. First set the min and max limits in the menu, **Left** and **Right** button select the digit, the **Up** and **Down** buttond change the digit value. If pressing **Left**, when the first digit is selected, editing will be cancelled and all changes to the value will be discarded. The first digit can only be set to '-' (minus) or ' ' (space). When the min and max values are set, select how the alarm should behave. The meter will automatically also exit hold mode (if set), if the alarm condition is met. Please consider the measurement unit, when setting up the min and max limits, eg. when in MΩ range, it is difficult to set small resistance values and MΩ values will be discarded, when editing min/max in the Ω range. Alarms are disabled, while in the menu. Limit mode is for useful as example for sorting parts, as a high voltage warning or adding a beep function to the diode mode.

## Logging mode
Logging to internal the flash, the log file will be saved in the LOGS folder, maximum 128 files are allowed in the folder. If averaging is enabled, the minimum, maximum and average values are saved to the log file, else only the current measured value will be saved. Turning on logging will automatically disable USB (charging is still possible), limits, hold mode and relative measurement. After turning on logging, all buttons except **PWR/REL** and **HOLD/SAVE** are disabled, so the meter has to be set-up as required, before turning on logging. In logging mode a short press of the **PWR/REL** button will turn the display on/off to save some power, a long press of the **HOLD/SAVE** button turns logging off again.

## 4-20mA mode
The main measurement value will be replaced with a polarity independent percentage value of a 4-20mA current loop. The measured current is displayed as the second measurement value. The current loop has to be connected to the **mA** socket and the **COM** socket. Relative measurement mode and manual range setting are disabled in this mode. Press any button from **F1** to **F4** to exit this mode. 

## RTD mode
Pt100, Pt500, Pt1000, Pt2000 sensors are supported. The main measurement value will be replaced with the calculated temperature. The actual resistance is displayed as the second measurement value. The RTD has to be connected to the meter like a resistor. Relative measurement mode and manual range setting are disabled in this mode. Press any button from **F1** to **F4** to exit this mode. 

## TC mode
Type B, E, J, K, N, R, S, T thermocouples are supported. The main measurement value will be replaced with the calculated temperature. The cold junction temperature has to be manually set using the menu (see Limit mode, for how to use the editing function). The measured voltage is displayed as the second measurement value. The TC has to be connected to the meter like any voltage source. Relative measurement mode and manual range setting are disabled in this mode. Press any button from **F1** to **F4** to exit this mode. Thermocouple probes have to be connected with the correct polarity.

## Menu usage
- **Left button** : go back one level
- **Right button** : enter submenu / activate or deactivate function / change parameter
- **Up button** : go up in the menu
- **Down button** : go down in the menu
- **Menu button** : show or hide the menu</br>

Activated settings and functions have a checkmark before them.

## Main menu
- **Limits**
- **Display settings**
- **Averaging**
- **4-20mA mode**
- **RTD mode**
- **TC mode**
- **DMM settings**

## Limits menu
- **Disabled** : limits function inactive
- **Alarm if inside window** : the meter will beep and the measured value will be displayed in red, when the measured value is inside the set minimum an maximum limits
- **Alarm if outside window** : the meter will beep and the measured value will be displayed in red, when the measured value is outside the set minimum an maximum limits
- **Set minimum limit**
- **Set maximum limit**</br>

The settings apply only to the current measurement mode. Every measurement mode has its own inviidual limit settings.

## Display settings menu
- **Clear** : clears the graph buffer and the minimum and maximum values
- **Show graph** : enable/disable the graph display
- **Show envelope** : enable/disable showing the minimum and maximum envelope on the graph display (only has an effect, if the averaging and vertical autorange is turned on)
- **Line interpolation** : enable/disable the line interpolation between measured points
- **Show statistics** : enable/disable the statistics (minimum / maximum / average) display (only has an effect, if the graph is turned off)</br>
- **Vertical autorange** : enable/disable autoranging on the vertical axis of the graph (envelope display is disabled, if this setting is turned off)
- **Vertical manual minimum** : set the minimum vertical value, this setting only applies to the current measurement mode
- **Vertical manual maximum** : set the maximum vertical value, this setting only applies to the current measurement mode </br>

The display settings, with the exception of **Vertical manual minimum** and **Vertical manual maximum** apply to all measurement modes.

## Averaging menu
- **Disabled** : averaging is disabled
- **3 Measurements (1s)** : sets the average size
- **9 Measurements (3s)** : sets the average size
- **15 Measurements (5s)** : sets the average size
- **30 Measurements (10s)** : sets the average size
- **180 Measurements (60s)** : sets the average size</br>

The averaging settings apply to all measurement modes.

## 4-20mA mode menu
- **Start** : enter the 4-20mA measurement mode

## RTD mode menu
- **Start** : enter the RTD measurement mode
- **PT100 sensor** : select the connected sensor type here
- **PT500 sensor** : select the connected sensor type here
- **PT1000 sensor** : select the connected sensor type here
- **PT2000 sensor** : select the connected sensor type here
- **Unit: Celsius** : select the measurement unit here
- **Unit: Fahrenheit** : select the measurement unit here
- **Unit: Kelvin** : select the measurement unit here

## TC mode menu
- **Start** : enter the thermocouple measurement mode
- **Type K sensor** : select the connected sensor type here
- **Type J sensor** : select the connected sensor type here
- **Type N sensor** : select the connected sensor type here
- **Type S sensor** : select the connected sensor type here
- **Type T sensor** : select the connected sensor type here
- **Type B sensor** : select the connected sensor type here
- **Type E sensor** : select the connected sensor type here
- **Type R sensor** : select the connected sensor type here
- **Unit: Celsius** : select the measurement unit here
- **Unit: Fahrenheit** : select the measurement unit here
- **Unit: Kelvin** : select the measurement unit here

## DMM setting menu
- **Backlight intensity** : enter the menu, to change the backlight intensity
- **HOLD/SAVE function** : enter the menu, to change what the long press of the HOLD/SAVE button should do
- **Reset all settings** : resets all settings back to default
- **Format filesystem** : formats the internal filesystem and creates the default folders

### Backlight intensity menu
- **10%** : sets the backlight intensity
- **20%** : sets the backlight intensity
- **30%** : sets the backlight intensity
- **40%** : sets the backlight intensity
- **50%** : sets the backlight intensity
- **60%** : sets the backlight intensity
- **70%** : sets the backlight intensity
- **80%** : sets the backlight intensity
- **90%** : sets the backlight intensity
- **100%** : sets the backlight intensity</br>

### HOLD/SAVE function menu
- **Long press for logging** : enables logging to the internal flash
- **Long press for screenshot** : enables saving a screenshot (BMP format)
- **Screenshot saves graph data** : enables saving the binary dump (floating point format) of the graph data, when saving a screenshot  
