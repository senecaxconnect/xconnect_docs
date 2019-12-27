# Server Agent

This is a required component to any server that you would like to be monitored by the xConnect
Remote Management Platform. 

This agent is responsible for collecting health information (also
called telemetry) as well as securely facilitating remote management features.

The latest version of the Server Agent installation executable is available on our download repository: [downloads.senecaxconnect.com](http://downloads.senecaxconnect.com)..

The Server Agent consists of 1 main background Windows Service, the **xConnect Agent Core**:

Within 

xConnect Engine
• This service is the telemetry collection engine that continuously polls various sensors
throughout the system. It is also responsible for transmitting this telemetry to the Secure
Gateway. Starts Automatically.
xConnect Updater Service
• This service handles touchless over the wire updates for all aspects of the Server Agent.
An update package can be delivered to the Secure Gateway, and the Server Agent will
automatically download and install this update unattended. Starts Automatically.
xConnect Agent Web Interface
• This service provides a local (or LAN accessible) web interface for managing and
configuring the Server Agent. Starts Automatically.
xConnect Remote Command Service
• This service handles remote commands that are securely transmitted through the
gateway. It is responsible for executing and tracking status of remotely triggered
commands. Commands or scripts that are currently supported are Windows CMD and
Windows PowerShell. Startup Type is Manual and needs to be changed to
Automatic if you’d like to use this feature.
xConnect Agent RESTful API
• This service provides a mechanism for 3rd party applications to ingest or transmit
telemetry in and out of the Server Agent. Startup Type is Manual and needs to be
changed to Automatic if you’d like to use this feature.
