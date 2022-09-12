___

# Compocloud Biofilter
___


___

## Biofilter-Widget
___

If the system is equipped with a biofilter and a biofilter blower, the widget for the biofilter is displayed after the windrow widgets. 
By clicking on the biofilter widget in the light grey area the biofilter section is being opened.

![Biofilter](/assets/images/Docs/Compocloud/Biofilter.png)

The widget shows the current status of teh Biofilter with the following values:

- **A**: The current temperature in the Biofilter

- **B**: The current pressure in front of the blower (between windrows and blowers)

- **C**: The speed setpoint for the biofilter blower. Usually, 100% corresponds to 50Hz.

- **D**: The current pressure after the blower (before the biofilter)

- **E**: Status of the blower. When the blower is operated, the fan rotates, in the event of a malfunction, the background is displayed in red. In the event of a fault, the alarm is also displayed in the header section.

- **F**: Mode On: If this mode is active, the character is highlighted like H, the biofilter blower runs continuously until the user changes the mode or a malfunction occurs. If this mode is active, the setpoint specification for the on mode (I) is also displayed. 

- **G**: Mode Off: In this mode, the biofilter blower is stopped.

- **H**: Automatic mode: In this mode, the biofilter blower is started and the speed is set via a controller. This tries to regulate the pressure in front of the blower (B) to a set value by adjusting the speed specification.

- **I**: Speed Preset Mode On: Appears only when the biofilter blower is in On mode. By pressing the symbol, a dialog for changing the setpoint is displayed. The value can be entered directly or adjusted by moving the slider. Pressing `Save` acknowledges the value. Pressing `Cancel` closes the dialog without any changes.

Changing the mode (F, G, H) and the speed specification (I) is only possible for ‘Operator’ or users with higher authorization.

___

### Settings
___

The settings can be opened by clicking on the menu item 'Parameter', a submenu item of the 'Biofilter'. To make changes, the user must be assigned to the operator or higher authorization group. After changing one or more values, they are transferred to the controller by pressing `Save`.

- **Setpoint Pressure before blower (A)**: Target pressure in the composting buildings

- **Biofilter Maximum Temperature (B)**: Maximum temperature in the biofilter

- **Hysteresis for Biofilter temperature (C)**: Hysteresis for maximum temperature

- **Interval width for automatic switch-off (D)**: (hidden and reserved for future use)

![Setting Biofilter Automatic](/assets/images/Docs/Compocloud/SettingBiofilterAutomatic.png)

___

### Functional description
___

The Biofilter consists of:

- Biofilter fan (regulated by frequency)- M<small>BLOWER</small>
- Temperature sensor in the Biofilter - T<small>BIO</small>
- Pressure senor intake side of the fan (from Boxes) - P<small>IN</small>
- Pressure Sensor pressure side of the fan (to Biofilter) - P<small>OUT</small>

##### Modes of Operation

The user can choose between 3 modes in the Biofilter-Widget:

- **ON**: continuous operation: The Biofilter-fan M<small>BLOWER</small> is turned on and the specification of the number of revelations is done by the user
- **OFF**: Biofilter fan  M<small>BLOWER</small> is turned off
- **AUTO**: Automatic operation: The Biofilter fan M<small>BLOWER</small> is turned on and the specification of the number of revelations is done by the regulator, who tries to keep a preset pressure.

Details about the different modes of the Biofilter fan can be found in the chapter `Biofilter-Widget`.

##### Operation

When the biofilter is in automatic mode, M<small>BLOWER</small> is started and the speed is adjusted via a controller so that pressure P<small>IN</small> (actual value) comes closer to the set point `A`. This regulation serves to maintain a negative pressure in the composting building. If a door is opened, it tries to counteract the higher pressure compensation. A warning is displayed at the same time. If the pressure sensor indicates an error (value is not between 4 and 20 mA), the exhaust air blower is operated at the minimum speed.

If the temperature T<small>BIO</small> exceeds the maximum temperature `B` , a warning 'Biofilter protection active' is issued. This warning remains in place until the temperature in the biofilter falls back below the maximum temperature `B` minus a hysteresis `C` . If this warning is active, the windrow and biofilter blowers are stopped.
