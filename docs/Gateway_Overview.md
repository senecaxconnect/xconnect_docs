# Gateway

This is a required component of the xConnect Remote Management Platform. This physical or
virtual gateway is responsible for being the encrypted tunnel between the Server Agents and the
Web Client Dashboard hosted in our cloud.

```mermaid
      graph LR
          A(Edge Devices) --> B(Agent)
          B --> A
          B -->|MQTT(1883)|C(Gateway)
          C -->|TLS(443)/MQTT(8883)|D(xConnect Cloud Dashboard - Azure);
          style C fill:#04acec
          linkStyle default stroke-width:2px,fill:none,stroke:black;
```

There are 4 installation options for this Secure Gateway:
- Arrow-hosted Gateway Container (also referred to as vBridge or Virtual Gateway)
- Physical (Turnkey)
- Virtual Machine
- Self-hosted Docker Container


## Arrow-hosted Gateway Container
Arrow offers a fully hosted version of the Secure Gateway software dedicated to your instance. To have this enabled in your subscription, please contact your Account Manager to understand subscription requirements.

Once your subscription has been enabled with this capability, adding a new gateway is as simple as a click of a few buttons.
 
## Physical (Turnkey) Gateway 
The physical gateway option greatly reduces setup time. This is a physical hardware device
provided by Arrow that has our hardened system image and most configuration details already
pre-configured from our factory.

The physical gateway highlighted in this guide is an ultra-small form factor embedded PC
provided by Arrow. The specifications of this physical gateway are:

| **SYSTEM**              |                                                                           |
|-------------------------|---------------------------------------------------------------------------|
| Manufacturer            | Seneca®                                                                   |
| Operating System        | Ubuntu Linux 18.04 LTS Server                                             |
| Memory                  | 8GB DDR3L 1600MHz                                                         |
| Processor               | Intel® Celeron® N3060 1.6-2.48Ghz 2MB Cache                               |
| USB                     | 4x USB3.0 (Front), 1x USB2.0 (Front), 2x Micro USB 2.0 (Side)             |
| Physical Security       | 1x Kensington Lock                                                        |
| Warranty                | 3 and 5 Year Warranty Options Available                                   |
| **MECHANICALS**         |                                                                           |
| Thermals                | 0ºC to 35ºC / 32ºF to 95ºF                                                |
| Power Draw              | 15W                                                                       |
| Cooling                 | Aluminum Extrusion Chassis Heatsink                                       |
| Mounting                | VESA/Wall Mountable, Brackets included, Rack shelf available for purchase |
| Dimensions (w x h x d)  | 7.5 x 1.75 x 4.25 inches / 191 x 46 x 108 millimeters                     |
| Weight                  | 3 lbs. / 1.4 kg                                                           |

Onboarding/Installation instructions are available in the [Getting Started](/xconnect_docs/Getting_Started) chapter. 

## Virtual Machine Gateway Option
The virtual gateway option is available when it is desired to use existing infrastructure to host the Secure
Gateway.

A Hyper-V Virtual Disk or VMWare OVA can be provided upon request and needs to be imported into the
 appropriate hypervisor. 
 
!!! note
    It is recommended to have 2 virtual switches attached to the VM. 1 Virtual Switch with connectivity
    to your internal LAN assets, and 1 Virtual Switch with Internet connectivity.

Professional Services are available to assist configuration of the virtual Secure
Gateway on your virtual machines.

Onboarding/Installation instructions are available in the "Getting Started" chapter. 

## Self-hosted Docker Container

We now support deploying an xConnect Gateway image via Docker. This option allows you to have 
an xConnect Secure Gateway deployed in minutes, granted you can supply a machine that Docker can be installed on.

You can use any Linux OS that supports the native Docker engine can be used to deploy the xConnect Gateway container. Other container engines and orchestration tools, like podman and kubernetes, are not currently supported. 

Container installation instruction files are available on our github page:
<https://github.com/senecaxconnect/xconnect_gateway_docker>

!!! note
    Docker for Windows is not officially supported, even through WSL. However,
    you could install a Docker-supported Linux OS within a Hyper-V VM on Windows and it would be fully supported.

Installation instructions are also available in the "Getting Started" chapter. 

