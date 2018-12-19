# Firmware/Configuration

It is very important that your M3D Crane Series printer has the most up to date software. In order to ensure the software is the newest version, you will need to identify what version of the software you are currently running. 

## Identifying Firmware Version

In order to identify your Firmware version you will need to go into your **Duet Web Control Console** and select the **Settings** option on the left side of the screen. Under the General tab, all of the **Firmware Versions** are listed. 

![Firmware Information listed in Settings](../.gitbook/assets/capture.PNG)

Once you have identified your software version and determined it is in need of an update follow this guide closely in order to successfully update your M3D Crane Series printer. These updates must be done in order. 

1. Firmware
2. Duet Web Control
3. Configuration Files

If you have an SD card reader, it is recommended that you simply remove the SD card from your M3D Crane Series printer, place it in your computer's SD card reader and drag and drop the Firmware updates. However the Duet Web Control and Configuration files must be updated using the process described below. 

{% hint style="info" %}
Updating your firmware is important in order to obtain the latest features and bug fixes. The Duet Maestro board uses a fork of RepRap firmware to control a 3D printer. 
{% endhint %}

## Firmware:

Our firmware updates, courtesy of user dc42 can be found here: [https://github.com/dc42/RepRapFirmware/releases/tag/2.02RC5](https://github.com/dc42/RepRapFirmware/releases/tag/2.02RC5)

| Version  | Description  | Author  |
| :--- | :--- | :--- |
| 2.02RC5 | [System Firmware](https://github.com/dc42/RepRapFirmware/releases/download/2.02RC5/DuetMaestroFirmware.bin) | dc42 |
| 1.22.5 | [Duet Web Control](https://github.com/dc42/RepRapFirmware/releases/download/2.02RC5/DuetWebControl-1.22.5.zip) | dc42 |

## Configuration Files:

These Configuration Files are for use with Duet Firmware 2.02RC5. This update is tested and official but still being actively updated. [https://github.com/PrintM3D/Crane/releases](https://github.com/PrintM3D/Crane/releases)

| Version | Description | Author |
| :--- | :--- | :--- |
| 2.02RC5: 1.35 | [M3D Crane Bowden](https://github.com/PrintM3D/Crane/releases/download/1.35/M3D_Bowden_135_pre.zip) | M3D |
| 2.02RC5: 1.35 | [M3D Crane Dual](https://github.com/PrintM3D/Crane/releases/download/1.35/M3D_Dual_135_pre.zip)  | M3D |
| 2.02RC5: 1.35 | [M3D Crane Quad](https://github.com/PrintM3D/Crane/releases/download/1.35/M3D_Quad_135_pre.zip) | M3D |

{% hint style="info" %}
**Warning: Updating your firmware can cause unintended consequences. Be aware that upgrading or downgrading to unstable firmware versions can cause unexpected bugs and issues. Use caution!**
{% endhint %}

## Upgrading System Firmware via the Duet Web Console

1. Download the desired firmware version from DC42's github page. This will be a _.bin_ or binary file called _**DuetMaestroFirmware.bin**_.
2. Download the ****_**iap4s.bin**_ file, this is necessary in order to update the firmware.
3. Go to the settings tab of the Duet Web Console and find the ****_**Upload File\(s\)**_ button. Note: this is not for uploading prints. Files uploaded here will be stored in the ****_**sys/**_ ****directory of the microSD card. Upload the _**iap4s.bin**_ and _**DuetMaestroFirmware.bin**_ files.

   ![aosmza6ID0m8KJ7A-uploadsysfiles.png](../.gitbook/assets/aosmza6id0m8kj7a-uploadsysfiles.png)

4. Once both files are uploaded successfully, go to the ****_**G-code Console**_. Send the command `M997 S0`. This will begin the process of upgrading Duet firmware.
5. When the firmware upgrade is completed, you can visit the _**Settings**_ ****tab in order to ensure that the _**Firmware Version**_ has been updated to the preferred version. 
6. If you prefer, you can now delete the _**iap4s.bin**_ and ****_**DuetMaestroFirmware.bin**_ files from the ****_**sys/**_ directory.

## Other Resources

1. [Duet 3D Wiki: Updating and Installing Firmware](https://duet3d.dozuki.com/Wiki/Installing_and_Updating_Firmware)
2. [Duet3D Forum](https://forum.duet3d.com/): For firmware and Duet specific questions
3. [Duet Fork of RepRap Firmware](https://github.com/dc42/RepRapFirmware)

