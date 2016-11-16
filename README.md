# vera-httpswitch
Vera plugin/implementation for creating devices that forward the "on" and "off" command via a HTTP(S) request to any other system

## Overview
The plugin implements the following services:
* urn:upnp-org:serviceId:SwitchPower1
* urn:upnp-org:serviceId:Dimming1
* urn:upnp-org:serviceId:WindowCovering1

That makes it compatible with the following standard device files:
* D_BinaryLight1.xml
* D_DimmableLight1.xml
* D_WindowCovering1.xml

## Installation
Go to "Develop Apps" feature in your Vera. Choose "Luup files" and upload the I_HttpSwitch1.xml file

## Creating a device
You create a device by navigating to the "Devlop Apps" menu item in your Vera. There you choose "Create device" and fill in the following fields (Minimum):
1. Description - The name of your device
2. Upnp Device Filename - One of the three device files mentioned above, i e D_BinaryLight1.xml
3. Upnp Implementation Filename - I_HttpSwitch1.xml downloaded from this repository

Click "Create device" and then reload your Vera Luup Engine

## Configure your device
When the device shows up in your Vera you will find four new variables under advanced settings:
* OnUrl - The url to be called when the device is switched "On" (or "Up/Open" for WindowCovering)
* OnMethod - The HTTP method to be used for the "On"-request, i e GET or POST
* OffUrl - The url to be called when the device is switched "Off" (or "Down/Closed" for WindowCovering)
* OffMethod - The HTTP method to be used for the "Off"-request, i e GET or POST

## Testing
I use this implemention to integrate some lamps and blind that are "hosted" in an [OpenNetHome](https://github.com/NetHome) instance into my Vera Edge. But the implementation should work for many other integration purposes where there is an HTTP/REST API.

## Limitations and future extensions
I have not had the need for more complex requests but for instance custom headers or request bodies could be added without to much work. Please let me know if this is of interest to someone and please feel free to contribute
