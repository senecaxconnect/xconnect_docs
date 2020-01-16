# Quick Start Guide

This guide is a condensed version of the installation process. Detailed instructions are available 
for each step of the installation process and can be found within this guide or on the navigation menu.

Please follow the steps below in the same order of operations as described:

1. Confirm Prerequisites
2. Configure Gateway
3. Configure Agent(s)
4. Configure Dashboard

## Prerequisites
<div class="aligncenter" style="width: 100%">
<p class="aligncenter" style="text-align: center">
    <img src="https://image.flaticon.com/icons/svg/394/394592.svg" style="max-width:25%;" alt="" />
</p>
</div>
Confirm the following before continuing your xConnect installation and configuration:

* Network Access has been configured or confirmed:
    * Agent System - Outbound Port TCP 1883 (MQTT)
    * Agent System - Outbound Port TCP 8885 (HTTP)
    * Gateway - Outbound Port TCP 443 (HTTPS)
    * Gateway - Outbound Port TCP 8883 (Secure MQTT)
* You've received credentials for the xConnect Web Dashboard ([senecaxconnect.com](http://senecaxconnect.com))
* Have a PC that can be used to complete IP address changes to gateway
    * Can be configured for the default static network of 10.0.0.0/24
      **or**
    * Is on the same DHCP network as the gateway and can obtain the IP of the gateway from DHCP server
    

## Gateway Setup (For Turnkey model)

1. Unbox your Secure Gateway and connect an Ethernet cable from Port 1 of the Gateway to 
an Ethernet port on the temporary configuration computer
2. Connect to the network

