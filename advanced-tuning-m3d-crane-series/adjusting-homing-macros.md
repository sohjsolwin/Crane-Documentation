# Adjusting Homing Macros

Whenever you press the homing buttons located in the **Machine Control** tab of Duet Web Interface, execute a `G28` command, or a G-code file is set to home prior to printing, the respective homing macro is executed. Below you will find a brief explanation of each of the relevant homing macros.   

## Homing Macros

The **sys/** folder, located in the root directory of the micro SD card contains the following files:

* **homeall.g**: This file contains G-code to home all three axes of the printer. This file is executed whenever the command `G28` is entered or whenever the **Home All** button on the Duet Web Interface is pressed.
* **homex.g**: This file contains G-code to home the X axis of the M3D Crane Series printer. This file is executed whenever the **Home X** button is pressed or when the  `G28 X` command is sent. 
* homey.g: This file contains G-code to home the Y axis of the M3D Crane Series printer. This file is executed whenever the **Home Y** button is pressed or when the `G28 Y` command is sent. 
* **homez.g**: This file contains G-code to home the Z-axis of this printer. It is called whenever you press the **Home Z** button on the Duet Web Interface or `G28 Z` is sent.



