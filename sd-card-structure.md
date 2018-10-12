---
description: An explanation of the SD card files.
---

# SD Card Structure \(new\)

One of the first steps of setting up your printer is getting access to and understanding the files stored on the microSD card. This guide will cover the basic structure of the files on the SD card. Follow the [Accessing Your SD Card](https://m3d.gitbook.io/promega-docs/getting-started/accessing-your-sd-card) guide for more assistance on how to get to the files located on the microSD card.

## File Structure

On the microSD card there are four different folders: _gcodes_, _macros_, _sys_ and _www_. These folders contain all the information the Duet board needs to operate properly. Below is a list of the folders and their purpose.

* _**gcodes**_: This folder contains _.gcode_ files that can be run by the Duet. If you upload print files through the Duet Web Console or via a microSD card they should be placed in this folder.
* _**macros**_: Any macro files that you create should be located in this folder. Macros are _.gcode_ files that can be executed to perform a repetetive task more quickly.
* _**sys**_: Configuration files of the printer. Contains important _.gcode_ files such as _config.g_ which are executed on startup. You will need to change files in this folder regularly.
* _**www**_: Holds all files necessary for the operation of the Duet Web Console. It is recommended not to mess with the files here unless you are familiar with web development.

## Sys Organization

As mentioned before, the _sys/_ folder contains all sorts of system files. The most important file is _config.g_. This file is executed on the start-up of the Duet Maestro board in order to configure the Crane settings. If you wanted to add a command to the start-up sequence, you should insert it in _config.g_. If you take a look at the config.g file you will see the following:

```text
; Configuration file for Duet Maestro (firmware version 2.02RC2 or newer)
; executed by the firmware on start-up
; Created by PrintM3D
; for the Crane Bowden
;

M98 Pgeneral.g                   ; Call General Configuration Module
M98 Pnetwork.g                   ; Call Network Module
M98 Pmotion.g                    ; Call Kinematics/Motor Module
M98 Pthermal.g                   ; Call Heater/Fan/Sensing Module
M98 Ptools.g                     ; Call Toolhead Module
```

**Configuration Files:**

{% tabs %}
{% tab title="general.g" %}
```text
; general.g
; Created by PrintM3D
; for the Crane Bowden
;
; The file sets initial movement phases and sets compatibility to RRFW.
;
; Logging Settings
;
;M929 P"eventlog.txt" S1  	     ; Uncomment This Line to Enable Event Logging
;
; General preferences
G90                              ; Send absolute coordinates...
M83                              ; Set relative extruder moves
M555 P1                          ; Set firmware compatibility Mode to RRFW
M501
```
{% endtab %}

{% tab title="network.g" %}
```text
; Network Settings for Duet Maestro
;
; For Crane Bowden
; by PrintM3D
;

; Machine name and Password
M550 PCraneBowden                ; Set machine name
M551 Pconductor                  ; Set password

; Ethernet Configuration
M552 P0.0.0.0 S1                 ; Enable Network and use Automatic DHCP
;M553 P0.0.0.0                   ; If necessary, set this to your netmask.
;M554 P0.0.0.0                   ; If necessary, set your network gateway.

; Enable/Disable Services
M586 P0 S1                       ; Enable HTTP
M586 P1 S1                       ; Enable FTP
M586 P2 S0                       ; Disable Telnet
```
{% endtab %}

{% tab title="motion.g" %}
```text
; motion.g
; Created by PrintM3D
; for the Crane Bowden
;
; This file declares drive kinematics, axis limits, and endstop settings.

; Drives
M569 P0 S1 D3 V0                 ; Drive 0 goes forwards
M569 P1 S0 D3 V0                 ; Drive 1 goes backwards
M569 P2 S0 D3 V0                 ; Drive 2 goes backwards
M569 P3 S1 D3 V0                 ; Drive 3 goes forwards
M350 X32 Y32 Z16 E16 I1          ; Set Microstepping
M92 X160 Y160 Z400 E96           ; Set steps per mm
M566 X900 Y900 Z90 E240          ; Set Maximum Jerk (mm/min)
M203 X9000 Y9000 Z1200 E12000    ; Set maximum speeds (mm/min)
M201 X1200 Y1200 Z90 E120        ; Set accelerations (mm/s^2)
M906 X1000 Y1000 Z1000 E1100 I30 ; Set motor currents (mA) and idle
M84 S60                          ; Set idle timeout


; Axis Limits
M208 X0 Y0 Z0 S1                 ; Set axis minima
M208 X230 Y230 Z250 S0           ; Set axis maxima

; Endstops
M574 X1 Y1 Z1 S1                 ; Set active high endstops
```
{% endtab %}

{% tab title="thermal.g" %}
```text
; thermal.g
; Created by PrintM3D
; for the Crane Bowden
;
; This file declares heater and fan settings.
; Heaters
M305 P0 T100000 B4006		         ; Thermistor Config for NTC 100k
M143 H0 S120                     ; Set temperature limit for heater 0 to 120C
M305 P1 T100000 B4006   	       ; Thermistor Config for NTC 100k
M143 H1 S265                     ; Set temperature limit for heater 1 to 265C

; Fans
; For Crane Bowden: F0 is Heatsink Fan, F1 is Part Cooling fans, F2 is Case Fan
M106 P0 T45 H1 F50                ; Set Heatsink Fan F0 to Thermostatic
M106 P1 H-1 F50                   ; Set Part Cooler Fans F1 to Gcode Control
M106 P2 S0.8 F50                  ; Set case fan always on at 80%
```
{% endtab %}

{% tab title="tools.g" %}
```text
; tools.g
; Created by PrintM3D
; for the Crane Bowden
;
; This file declares tools, bed leveling, and flags settings for override.
M563 P1 D0 H1                    ; Define tool 0
G10 P0 X0 Y0 Z0                  ; Set tool 0 axis offsets
G10 P0 R0 S0                     ; Set initial tool 0 active and standby temperatures to 0C

; Manual Bed Leveling
M558 P0

T0
```
{% endtab %}
{% endtabs %}

### "Everything is gcode." 

{% tabs %}
{% tab title="general.g" %}
| gcode  |  |
| :--- | :--- |
| `G90` | Sets coordinates to absolute relative to the origin of the machine. |
| `M83` | Sets extrusion values as relative positions. |
| `M555 P1` | Sets firmware so as it's input and output is similar to other established firmware. In this case the P argument is 1, for RepRap\_firmware. |
| `M501` | This allows the stored parameters to be loaded at startup. It can also revert parameters to stored values after experimenting with them. |
{% endtab %}

{% tab title="network.g" %}
| gcode |  |
| :--- | :--- |
| `M550 PCraneBowden` | This sets your Machine's Name. |
| `M551 Pconductor` | This sets your Machine's Password. |
| `M552 P0.0.0.0 S1` | Sets the IP address as well as enable/disables the network interface and allows Automatic for Dynamic Host Configuration Protocol. |
| `M553 P0.0.0.0` | This will set up your netmask. |
| `M554 P0.0.0.0` | This will set your network gateway.  |
| `M586 P0 S1` | Enables Hyper Text Transfer Protocol. |
| `M586 P1 S1` | Enables File Transfer Protocol.  |
| `M586 P2 S0` | This Disables Telnet, or the network protocol that allows a user on one computer to log onto another computer that is part of the same network. |
{% endtab %}

{% tab title="motion.g" %}
| gcode |  |
| :--- | :--- |
| `M569 P0 S1 D3 V0` | This will set the motor driver direction, enable polarity and step pulse timing. For in depth explanations of the P, S, D, and V values click [Here.](https://duet3d.dozuki.com/Wiki/Gcode#Section_M586_Configure_network_protocols) |
| `M350 X32 Y32 Z16 E16 I1` | This sets your micro-stepping mode, X, Y, and Z represent the axis, E is the extruder, and I is the micro-step interpolation mode for the specified drivers. |
| `M92 X160 Y160 Z400 E96` | This sets axis steps per unit, allowing programming of steps per mm for motor drives. |
| `M566 X900 Y900 Z90 E240` | This sets the allowable instantaneous speed change, or "max Jerk" of each motor when changing direction. |
| `M203 X9000 Y9000 Z1200 E12000` | This will set the maximum feed-rates that your machine can do in mm/min. |
| `M201 X1200 Y1200 Z90 E120` | This sets the max acceleration that axes can do in mm/second^2 for print moves. |
| `M906 X1000 Y1000 Z1000 E1100 I30` | This will set the motor currents. Here X, Y, Z, and E, are the drive motor current and I is the motor current idle factor. |
| `M84 S60` | This will set the number of seconds of inactivity allowed before the stepper motors will go into idle mode. |
| ~~`M208 X0 Y0 Z0 S1`~~ | This will set the minimum limits for axis travel. |
| `M208 X230 Y230 Z250 S0` | This will set the max limits for axis travel, these limits when set, are also the assumed positions when an endstop is triggered. |
| `M574 X1 Y1 Z1 S1` | This allows for Endstop configuration, which will define the type of endstop the printer has for each axis. 1=low end, 2=high end and the S parameter defines if the input is active high S1 or low S2. |
{% endtab %}

{% tab title="thermal.g" %}
| gcode |  |
| :--- | :--- |
| `M305 P0 T100000 B4006` | This sets the temperature sensor parameters. P is the heater number, T is the thermistor resistance, and B is the Beta value of the thermistor. |
| `M143 H0 S120` | This sets the maximum heater temperature. H is the neater number and S is the max temp. |
| `M106 P0 T45 H1 F50` | This will set the Fan On configuration. P is the fan number, T is the temperature control range, H enables thermostatic mode and select hearers monitored. F is the Fan PWM frequency. |
| `M106 P1 H-1 F50` | This will set the Fan On configuration. P is the fan number, T is the temperature control range, H enables thermostatic mode and select hearers monitored. H-1 disables thermostatic mode. F is the Fan PWM frequency. |
{% endtab %}

{% tab title="tools.g" %}
| gcode |  |
| :--- | :--- |
| `M563 P1 D0 H1` | This will Define or remove a tool. P is the tool number, D is the extruder drive, and H is the heater. |
| `G10 P0 X0 Y0 Z0` | This defines Tool Offsets. P is the tool number, X is the X axis offset, Y is the Y axis offset, and Z is the Z offset squared. |
| `G10 P0 R0 S0` | This defines Tool Offsets. P is the tool number, R is the Standby temperature and S is the Active temperature. |
| `M558 P0` | This will set the Z probe type where P is the probe type. |
| `T0` | This is the activation of tool head Zero |
{% endtab %}
{% endtabs %}

## **Other Files**

In the _sys_ folder you will find many other files which handle other important aspects of the printer. Observe the list below for an explanation of the different files.

* _**config.g**_: This file is called upon the boot-up of the Duet board. Place G-code commands here in order for them to be executed on start-up. This file calls multiple machine files listed above with the `M98` command.
* _**homex.g**_**,** _**homey.g**_**,** _**homez.g**_ and _**homeall.g**_: These files operate the homing procedure. Follow [Homing the Printer](https://m3d.gitbook.io/promega-docs/getting-started/homing-the-printer) for more help on homing the printer, and [Adjusting Homing Macros](https://m3d.gitbook.io/promega-docs/firmware-guides/adjusting-homing-macros) in order to adjust the homing macros.
* _**pause.g**_ this `M25` will pause your print at it's current position.
* _**stop.g**_ when the firmware finishes the moves left in it's buffer, the macro `M0` _**stop.g**_ is called this will lift z axis to make clearance for your print, move the bed forward so the print can be removed, then will turn off the heaters, motors, and any part cooling fan that is in use.
* _**start.g**_  `M23` will select your file and __`M24` will set your printer to start printing the selected file.
* _**resume.g**_  `M24` __this will resume a print that was previously paused. It will resume printing from the point at which it was paused. Use `M23` to restart the print from the beginning. 
* _**bed.g**_ is executed when a `G32` is called. This command is more widely explained in our [**Bed Leveling Guide.**    ](https://crane.printm3d.com/~/drafts/-LON0jJTdJoUd9FoPX0S/primary/manual-bed-leveling)\*\*\*\*
* _**sleep.g**_ when the printer has shut down and all the motors and heaters are turned off, _**sleep.g**_  `M1` can be send which will wake it up again.

\*\*\*\*

