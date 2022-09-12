___

# Compocloud Windrow
___



___

## Windrow-Widget
___

A widget displays all measured values and status information for a windrow.

![Windrow-Widget](/assets/images/Docs/Compocloud/COMPOcloud_Windrow-Widget_EN.png)

The following values can be observed:

- **A**: Name of the windrow.

- **B**: The control temperature. This value is calculated from the measured temperature values and the set calculation method (see D) 

- **C**: Blower status: Rotates when the blower is in operation. In the event of a malfunction of the blower, it is highlighted in red.

- **D**: The set method for calculating the control temperature. Possible values are:

    - **Average**: Calculates the arithmetical mean of all temperatures
    - **Minimum**: The lowest temperature measured
    - **Maximum**: The highest temperature measured
    - **Temperature 1 - Temperature 5**: The measured value of a particular temperature sensor is used.

- **E**: Temperature 3: Measured temperature of sensor 3 (the top sensor for TML-3)

- **F**: Temperature 2: Measured temperature of sensor 2

- **G**: Temperature 1: Measured temperature of sensor 1. This sensor is located in the tip of the lance.

- **H**: Signal quality: Loss of signal from the temperature lance to the TML receiver. The higher the value (Attention! Negative number!), the better the received signal. 

|     from            	|     until        	|     Quality                   	|
|--------------------	|------------------	|--------------------------------	|
|     <= -100dBm     	|     -90dBm       	|     Very bad signal		    	|
|     -90dBm         	|     -80dBm       	|     Bad signal		        	|
|     -80dBm         	|     -70dBm       	|     Average signal		      	|
|     -70dBm         	|     -60dBm       	|     Good                        	|
|     -60dBm         	|     >= -50dBm    	|     Very good                   	|

- **I**: Battery voltage: Only assumed value, real voltage can differ.

|     from       	     |     until          	|     Capacity      	          |
|--------------------	 |------------------	|-------------------------------- |
|     2900mV    	     |     3100mV       	|     Empty           	          |
|     3100mV    	     |     3300mV       	|     Nearly empty                |
|     3300mV    	     |     3500mV       	|     Nearly full                 |
|     3500mV    	     |     3600mV       	|     full           	          |
|     -60dBm    	     |     >= -50dBm    	|     Very good       	          |

- **J**: Timespamp of the last time a data point was received from the device (IoT-Gateway)

- **K**: Irrigation quantities. On the left is the current daily quantity, on the right the target daily quantity. It is only shown if this rent is equipped with an irrigation valve. 

- **L**: Name of the current batch. If no batch is assigned, three dots ('...') are displayed instead of the name.

- **M**: Edit the batch for this windrow. If this element is clicked, the dialog for editing the batch appears.

___

### Editing the Charge
___

When clicking on the Edit-icon (M), a dialog opens.
The user can choose the next activity here. Possible actions are:

- **Add material**: This button is only displayed if there is no batch on this windrow. If you press this button, an input field for the name of the new batch is inserted below. Enter a new, unique name for this batch and press `Add Material`. after adding, the name should be displayed in the position `J`.
- **Transfer material**: This button is only displayed if there is a batch on this windrow. If you press this button, a selection list of possible target windrows will appear. Choose a windrow as the destination for this batch and press `Transfer Material`.
- **Remove Material**: Removes the material (batch) from a windrow. This batch is then no longer present in a windrow. If you press this button, you will be asked if you really want to remove this batch. If yes, confirm with `Yes` otherwise `No`.

___

### Windrow blower
___

In the lower section, the possible operating modes (A1-A4) of the blower are shown. The active mode is highlighted (See A4)

![Windrow Blower Control](/assets/images/Docs/Compocloud/MietenSteuerung.png)

##### Continuous operation (A1)
Blower is being started by the user by pressing A1 and confirming the following dialog. It runs until this blower is being stopped by the user by selecting another mode or by a malfunction.

##### Turned off (A2)
The blower is being stopped.

##### Interval-mode (A3)
The blower is switched on or off for a set time. After the end of the break time (switched off), the operating time (switched on) is started again.
The setting is made via the parameters page of this windrow.

##### Temperature-Mode (A4)
The blower is operated similarly to the interval mode. However, the operating time and the pause time from the control temperature (B) are determined via linear functions.
The setting of temperatures and times is done via the parameters page of this windrow.


##### Local Modus (AM)
If blower is equipped with a local control selector (LCS), blower can be operated from the LCS or the control system. If a LCS is available for this windrow, the selector is mostly located on the front of the cabinet door. A bi-color LED indicates the status of the blower. Red, if the blower is faulty (e.g. Motor protection switch tripped, Motor temperature high,...), and green, if running (Contactor closed).


Positions of LCS:
- **Local (Hand)**: Blower runs permanently, also if PLC is down.
- **Off**:Blower is stopped.
- **Remote (Auto)**: Blower controlled by control-system (PLC). Select one of operation modes (A1-A4) listed above.

If LCS is switched to mode `Local` (Hand) or `Off` at LCS, blower control via PLC and mandy is inhibited. 

![Windrow Blower Local Control](/assets/images/Docs/Compocloud/COMPOcloud_WindrowControlLocal.PNG)
___

### Irrigation
___

Directly below the mode selection of the windrow blower, the possible operating modes (`B2-B4`) of the irrigation are displayed. The active mode is highlighted (see `B3`). This part will only be displayed if there is an irrigation valve for this windrow.

![Rental Irrigation Control](/assets/images/Docs/Compocloud/MietenSteuerungIrrigation.png)

##### Status valve (B1)
Shows whether the irrigation valve is open or closed (crossed out). Also shown as open if emptying is active for this windrow after irrigation.

##### Continuous Irrigation (B2)
Starts irrigation for this windrow until the user switches the mode or an error occurs. The quantity is added to the current daily quantity. If the irrigation is stopped and the outside temperature is below 5°C, this part of the system is being emptied. The duration of the emptying can be parameterized in the general settings.

##### Switched off (B3)
Irrigation is disabled for this windrow.

##### Automatic irrigation  (B4)
The user can set a cycle quantity and a daily target quantity in the setting for the windrow. Based on these settings, the number of cycles and the next start time (B6) are calculated. If the current time is equal to the next start time, the cycle quantity (daily target quantity/number of cycles) is dispensed. The current daily amount is updated after completion of irrigation and displayed in the windrow widget below K and B5. If the irrigation is stopped and the outside temperature is below 5°C, this part of the system is emptied. The duration of the emptying can be parameterized in the general settings.

___

### Windrow Parameters
___

On this page you can make the setting for this windrow.

#### Interval settings
Settings for the windrow fan in `Interval` mode. If the blower is in this mode, it is switched on for the set `runtime` and switched off for the set `pause time`. 

![Setting Interval](/assets/images/Docs/Compocloud/COMPOcloud_Windrow-Settings-Interval_EN.PNG)

#### Automatic settings

Settings for the windrow fan in `Temperature` mode. With the help of a linear function, the running time and pause time are determined depending on the control temperature of the windrow. The left side describes the minimum running time or pause time at a desired temperature. The right side describes the maximum running time or pause time at a desired temperature. The running time or pause time is limited by these values. 

![Setting Automatic](/assets/images/Docs/Compocloud/COMPOcloud_Windrow-Settings-Automatic_EN.PNG)

#### TML-Settings

- **Serial Number**: Serial number of the temperature lance to be assigned to this windrow. For TMLv4 with WLAN, only the last eight digits have to be entered.
- **Control Temperature**: Selection which temperature should be used for the calculation of the running and pause times of the windrow blower in the 'Temperature' mode. For details see chapter `Windrow-Widget`.

![Setting TML](/assets/images/Docs/Compocloud/COMPOcloud_Windrow-Settings-TML_EN.PNG)

#### Irrigation
Will only be displayed if this windrow is equipped with an irrigation valve.
-	**Daily amount**: Amount of water to be dispensed every day. Once this amount is reached, irrigation is stopped for this day.
-	**Interval quantity**: Amount to be applied to each irrigation cycle.


![Setting Irrigation](/assets/images/Docs/Compocloud/COMPOcloud_Windrow-Settings-Irrigation_EN.PNG)
