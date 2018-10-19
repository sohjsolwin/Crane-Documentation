# M3D Crane Bowden Quick Start Guide \(new\)

{% hint style="warning" %}
The M3D Crane Bowden contains sensitive electronics, delicate mechanical parts, and an electrical heating system. Please exercise all applicable safety precautions and follow this guide closely to avoid damage to your M3D Crane Bowden, to avoid injury to yourself or others, and insure proper operation.
{% endhint %}

## Setting up after unboxing your printer: {#gmail-setting-up-after-un-boxing-your-printer}

After removing your M3D Crane Bowden from the box, remove all the plastic wrapping being careful not to cut any of the sensitive parts of the device, such as the cables. Your M3D Crane Bowden should look like this:

![](.gitbook/assets/20181004_023218_001%20%281%29.jpg)

Remove the bolts at the bottom of each upright rail, as shown below. Setting them aside briefly:

![note the bolts sticking out of the rails](.gitbook/assets/image%20%2810%29.png)

![](.gitbook/assets/image%20%285%29.png)



![](.gitbook/assets/20181004_022851-0.jpg)

{% hint style="warning" %}
Inspect your M3D Crane Bowden for any damage that may have occurred during shipping. Every precaution has been made to prevent this, however it is advisable to give all the components a thorough inspection before operation. If any issues are discovered, document the damage by taking an image of the affected area and contact M3D immediately.
{% endhint %}

 As long as no issues are discovered, you are ready for mechanical assembly. 

## Assembly: {#gmail-assembly}

Being careful not to stress or pull any of the cables, have a friend assist you in raising the upright rails; be sure to **align the bolt holes**.

If you aren't able to hold the upright in place, get someone's help to steady it. Line up the bolt holes\(that previously housed the bolts you removed\) and begin slowly tightening the bolts; first hand tighten, then slowly tighten more firmly with the provided **Allen Key**.

![](.gitbook/assets/20181004_023937_004.jpg)

Ensure that all motor cables are connected. These are part of the **black ribbon cable**. You can identify the correct motor cable by looking at the **yellow tags reading 'X, Y, and Z'.** The motor connections are made up of 4 wires, while the associated endstop cable is a three wire cable directly beside the 4-wire cable for the respective motor; the only motor without an endstop is the extruder.

![](.gitbook/assets/20181004_024627.jpg)

![](.gitbook/assets/20181004_024947.jpg)

Connect the two gray ribbon cables labeled '1' and '2' and connect them to their respective ports on the back of the LCD assembly, 'EXP1' and 'EXP2'. **Be careful not to cross these connections as it may damage the LCD Screen.**

![](.gitbook/assets/20181004_025210.jpg)

![](.gitbook/assets/20181004_025303.jpg)

After making the connections, use the provided bolts and Allen Key to secure the LCD to the front of the M3D Crane Bowden.

![](.gitbook/assets/20181004_025605.jpg)

{% hint style="danger" %}
Prior to exiting this section, please double check all connections, and place your crane on a flat surface. Ensure the Power Switch is Off\(O\), double check that your voltage is set appropriately for YOUR area\(consult local authorities if you are unsure\). **Failure to do this can irreparably harm the electronics in your printer.**
{% endhint %}

Once your M3D Crane Bowden is complete it should look like this:

![](.gitbook/assets/image%20%286%29.png)

## First steps with your M3D Crane Bowden: {#gmail-first-steps-with-your-m-3-d-crane-bowden}

Once your M3D Crane Bowden is assembled and powered on, follow these steps to printing your first test print. The M3D Crane Bowden comes with a [**test print pre-loaded on it's SD card**](https://www.thingiverse.com/thing:170922/files). This print is very important as it will be used to make sure your M3D Crane Bowden is calibrated correctly.

![Calibration Cube and Circle](.gitbook/assets/calibration_cubecircle_preview_featured.jpg)

The very first step is to **Home** your M3D Crane Bowden. To do this simply select **Home** **All** on your Menu screen.

## Loading and Unloading Filament:

Once your printer has been **homed** you will need to **heat the nozzle** in order to **load your filament** and start your print.

The temperature of the nozzle will be dependent upon the type of filament you choose to use for your first print, for the included test print we ask that **PLA** be used. Recommendations vary on the best temperature to use for PLA, but for this test print we ask that you **heat the nozzle to 200C.**

Once your nozzle is up to temp you may insert your **PLA** filament. Send **filament** through the entrance of the **extruder** **located at left side of the printer**. While **compressing the leaver on the extruder, feed the filament on through the bowden tube and into the hot end**. As the filament hits the hotend, it will heat up and start to liquefy. The filament will then start to seep out of the nozzle.

It is recommended to **extrude 50 to 100 mm** of filament to ensure correct loading, heating, and that there are no blockages in the nozzle or bowden tube. 

To **Unload the Filament** simply maintain your nozzle temperature **while depressing the leaver on the extruder. \(This will disengage the extruder gears so the filament will be free to move\)** Grab hold of the filament and pull it out with a sweeping, fluid motion. The filament will be slide up and out of the nozzle, out of the bowden tube and out the extruder.  

## Slicing and Printing the first model: {#gmail-slicing-and-printing-the-first-model}

Now that you have printed the test print that came on the SD card of your M3D Crane Bowden, you can now move on to finding, slicing and printing your own 3D models!

You may choose to create your own 3D models with software such as [Autodesk's Fusion 360](https://www.autodesk.com/products/fusion-360/overview), or[ Openscad](http://www.openscad.org/downloads.html), however you may wish to start printing models that are already available for download. You can find free models for 3D printing at [Thingiverse](https://www.thingiverse.com/), or you can try a few from [this list](https://all3dp.com/1/free-stl-files-3d-printer-models-3d-print-files-stl-download/).

Once you have found your ideal 3D model and downloaded it's **STL** file, it's time to download a **Slicer**. A **slicer** takes a 3D drawing \(most often in .STL format\) and translates this model into individual layers. It then generates the machine code \(g.code\) that the **printer** will use for **printing**.

While there are several great Slicers out there, both free as well as paid we recommend [Cura](https://ultimaker.com/en/products/ultimaker-cura-software). Download and install the latest version of **Cura by Ultimaker**.

The M3D Crane Bowden has several Cura **Printing Profiles** that have been pre-configured, each to the optimal settings within Cura for a selection of different material types. You can find and download the first of those here within this point release:  [https://github.com/PrintM3D/Crane/releases/tag/1.1](https://github.com/PrintM3D/Crane/releases/tag/1.1) -- you can also find the latest version of the Bowden SD Card here in case you need it.

Once you have selected and downloaded the Cura Printing Profile you will need for the material you are printing in, you can **Import the profile into Cura and Save it.** You can find these options in the Menu Bar at the top of the slicer's window. For additional information on Cura settings please go [here](https://ultimaker.com/en/products/ultimaker-cura-software).

Now that your settings are optimized with the imported printer profile, you can slice your model. Simply click the "**prepare to print**" button in the lower right corner of the slicer to generate your g.code. **Save this new file to your computer.** 

Your model is now saved on your hard drive. Just follow the instructions for how to use your [Duet Web Control Interface](https://crane.printm3d.com/~/drafts/-LMGnnAn5_tvVgYh8GkJ/primary/v/master/duet-web-interface-new), to learn how to upload your new STL file. Enjoy watching your models come to life! 

