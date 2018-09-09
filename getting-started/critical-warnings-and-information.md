# \(Edit details\) Critical Warnings & Information

The M3D Crane is an professional technology product. The user assumes all responsibility for proper operation and acknowledges that they understand the operation and standard practices of additive manufacturing. The user assumes all responsibility for its proper use and agrees to follow the directives below to ensure a safe and working unit before any other operation.

## Warnings

1. DO NOT TOUCH PRINTER WHILE OPERATING The Crane is a powerful machine. While the Crane is moving or printing you should not reach into the buildspace.
2. AVOID MOVING WITHOUT POWER
3. MOVE MOTORS/BED/EXTRUDER SLOWLY

   Moving motors generates power on all printers and can damage your board. There is no clear indicator of the power you are generating however when moving very fast the fans may start to turn. If you can hear the fan moving air, you're close to voltages that will break the duet regulator \(more than 28V\). Moving components about 50mm/s is safe. It is best to always move components while the system is powered.

4. DISABLING MOTORS

   When you disable motors the printhead may drop extremely slowly to the limit switch. This is normal behavior and requires rehoming.

5. ESD SAFETY:

   The Duet contains an ARM class 2 processor, we recommend you use a wrist straps when touching any wires that could send shocks to the main processor and fry it.

6. DON'T USE AN ESD WRIST STRAPS TIED TO A SURGE STRIP

   The printer is grounded. If you wire the strap wrong it can cause a short circuit through your body whenever you touch the printer.

7. USE UNDER SUPERVISION

   Use product in locations where nothing can catch on fire should the worst occur. The Crane is constructed out of metal and fireproof materials. Still, PLA and other filaments can burn fire if the printer is used improperly.

8. MAXIMUM EXTRUDER SPEED

   It is a common misconception that printhead travel movement speed \(i.e. 60 mm/s\) is the limiting factor when printing. However, it is extruder volumetric \(or mass\) flow rate that is the true limiting speed in most conditions. It is not easy to be able to exceed 9 mm^3/s \(PLA\) and 12 mm^3/s \(Higher temp materials like PETG, ABS\) except in special cases. To calculate flow rate multiple head speed, layer width, and layer height. For example: 45mm/s movement, 0.3 mm layers and 0.5 mm wide would be 6.75mm^3/s.

9. Z SPEED

   The bed current, acceleration and speed are configured for worse case scenarios like heavy prints. You can increase speeds when printing lighter items or depending on your application of the printer.

10. BED TEMPERATURE

    If you are using a glass print bed, give the printer an extra few minutes to reach temperature. In open air, the glass surface will be 5-10 C cooler than the bed temperature readouts from the thermistor.

11. FRAME CAN BE SHARP

    The frame of the printer is metal and could contain sharp edges. Use caution when moving the printer or moving around the printer. Keep your hands out of the machine during operation and be careful when lifting.

12. BURN HAZARD

    BED and NOZZLES are hot!

13. USE CAUTION WHEN REMOVING PRINTS

    The best strategy is to let the bed cool, most prints pop off by themselves.

14. REMOVING DUET SD CARD DISABLES FEATURES

    The Duet relies on its microSD card to serve as memory, storage for the LCD menu structure, duet webhost, and basic configurations. Without this card you can not connect over ethernet or use the LCD, however USB will still work. We do not recommend removing it. There is an SD card slot under the LCD providing a card slot physically moving print Gcode files, or use the web interface to upload Gcodes.

