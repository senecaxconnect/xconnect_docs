# Agent Installation
If you purchased an appliance from Seneca, it may already contain the xConnect Agent.

However, it is highly recommended to always download and install the latest version available at time of setup.

## Installation (One-liner)
1. Open a Windows Powershell terminal with Administrative privileges
2. Copy then Paste/run the following command into the admin powershell terminal:

    ```powershell
    Set-ExecutionPolicy Bypass -Scope Process -Force; [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -useb 'https://download.senecaxconnect.com/files/Agent/xConnectInstall.ps1')))
    ```

## Installation (Manual)
1. Download the latest xConnect Agent, found at www.senecaxconnect.com (Click the Download Agent link)
2. Proceed with installation (Run as Administrator), completing all prompts.

    !!! note
        Make sure to run as Administrator! (Right-click the installation file and click Run As Administrator)
 

## Configuration (Cloud-Enablement)
1. Access the Agent Configuration Portal by going to
http://localhost:8886/ (Also available by double-clicking the xConnect icon in the system tray)
2. Click on the “Settings” navigation item at the top of the
page. 
3. In the “Gateway Address:” field, enter
the hostname or IP address of your gateway provided to your during Virtual Gateway setup.
4. Once the IP address and the hostname of the gateway
has been entered, click the Save Changes button