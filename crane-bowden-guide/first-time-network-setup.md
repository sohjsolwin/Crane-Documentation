---
description: >-
  This section provides instructions on adding your printer to your network for
  the first time.
---

# First time Network Setup

Connecting to your Crane via your local network is very useful as you get access to the **Duet Web Console**. You can connect your Crane to your local network via the **Ethernet port on the Duet Maestro.** Once the network settings are properly configured, you will be able to connect to the **Duet board** and access the **Duet Web Console**.

## First-Time Start-up {#first-time-start-up}

{% hint style="info" %}
The M3D Crane Series printers were pre-configured to easily work with the most common network configuration, **DHCP**. If however you have a more complex network configuration set up it may be necessary to further edit your network settings.
{% endhint %}

Pre-configured network settings are loaded onto every SD card before the printer goes out our door. these network settings utilize **DHCP** in order to get an IP address from your router. This should allow your printer to connect automatically to your network. 

First ensure that the Ethernet cable is connected properly to the Duet board and turn the board on. It will take a while for your printer to boot and connect to the network \(~30 seconds\). When your Ethernet cable is properly connected to the board, the **green LED should be flashing and the yellow LED should be soli**d.

![](../.gitbook/assets/1nxumrea7qvltded-flashingethernet.gif)

Once connected via **Ethernet** your ****M3D Crane Series printer will display an **IP address** on it's LCD screen. After your printer has had the time to start up, open a browser tab on a computer **connected to the same network as the printer**. In the browser URL textfield enter the IP address displayed on the printer's LCD screen. 

 If the connection is successful the **Duet Web Consol**e should be shown. You have completed the network setup.

 

