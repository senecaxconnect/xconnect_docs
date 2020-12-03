# Turnkey Gateway Setup

You have 2 connectivity options.

**Option 1 (Plug and Go)**<br>
This is the easiest of the 2 options to get up and running quickly. However, this will 
require a DHCP and internet enabled network connection.

**Option 2 (Set Static IPs of Gateway)**<br>
This option should be taken if you would like to assign static IP or IPs to the network ports of the gateway.
A PC and an ethernet cable that can connect to the gateway is required for this option.

## Option 1 - Plug and Go (DHCP/Single Network)
With this option you can be up and running in minutes without any special setup steps. However, 
all agent systems must be on the same network as the gateway.

1. Power on your Secure Gateway Device
2. Connect **PORT 2** to an **Internet-Enabled** DHCP network

You are all done! 


## Option 2 - Static IPs (Dual Network)

For configuration you will temporarily use an available computer
and its web browser. Also, due to security reasons the default password will need to be obtained from 
our support team by emailing [support@senecaxconnect.com](mailto:support@senecaxconnect.com)

1. Power on your Secure Gateway Device and connect an
Ethernet cable from **PORT 1** of the Gateway to an
Ethernet port on the PC that can be used for configuration.

2. Set a static IP on your PC to 10.0.0.x, where x is anything between 1 and 254 except for 250

3. Access the gateway portal by going to http://10.0.0.250:8885/ in a web browser from your PC. 
    !!! note
        (NOTE: 10.0.0.250 is the default
        IP. If the gateway IP has changed, use the new one
        instead).
4. Log in to the Gateway with the following credentials:

    Username: admin<br>
    Password: **<e-mail [support@senecaxconnect.com](mailto:support@senecaxconnect.com) for password>**

5. Click “IP Address Config” on the top menu

    You can choose to use 1 or 2 NICs on the gateway. Using 2 NICs is recommended for extra security.

    **Single NIC Use:**
    <br> Select Static and Enter the IP Address, Subnet Mask, Gateway, and DNS server(s) for the **Primary Network**
    
    **Dual NIC Use (Recommended):**
    <br>  Select Static and Enter the IP Address and Subnet Mask only for the **Primary Network**
    <br> Select Static and Enter the IP Address, Subnet Mask, Gateway, and DNS server(s) for the **Secondary Network**

    !!! note
        If you are configuring IP addresses on both NICs, you will need to ensure
        there is an active network plugged into both NICs. Only NICs that have active connections
        will appear in the dropdown menu in the IP Address Configuration screen
    
    This is an example of the network configuration for Dual NIC Setup:<br>
    Primary Network - 192.168.1.0/255.255.255.0<br>
    Secondary Network - 10.252.13.0/255.255.255.0<br>
    ```mermaid
      graph LR
            c1-->b1
            a1(Internet)
            b1(Gateway NIC 1<br>192.168.1.200/24)
            b1---b2
            b2(Gateway NIC 2<br>10.252.13.5/24)-->a1
            c1(Agent NIC<br>192.168.1.5/24);
            linkStyle default stroke-width:2px,fill:none,stroke:black;
    ```
    
6. Click ‘Save’ to finalize the network interface update

7. Wait 1-2 minutes for the gateway to reboot. 

8. Verify you can successfully ping the IP address you
specified as “primary” from the same network which your
Server Agents will reside

