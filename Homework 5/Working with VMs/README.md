# Homework 5 - Working with Virtual Machines

This guide will walk you through the process of setting up a Windows Virtual Machine (VM) in the Azure cloud. This VM will serve as your environment for working with NoSQL databases using Cosmos and the NoSQL API. Please read through the entire guide before deployment to avoid any cost overruns. Incorrect steps may lead to charges beyond your Azure allowance.

## Prerequisites

Before you begin, make sure you have the following:

- An Azure account
- Access to the Azure portal

## Step 1: Create a Windows VM

Follow the Microsoft Learn tutorial "Quickstart - Create a Windows VM in the Azure portal" to create your VM. [Link to Tutorial](https://learn.microsoft.com/en-us/azure/virtual-machines/windows/quick-create-portal)

### Important Configuration Steps

In the tutorial, pay attention to the following custom settings to prevent cost overruns:

1. **Image Selection**: Choose the Windows image recommended in the tutorial.

    ![Image Selection](../../images/hw5-img1.png)

2. **Virtual Machine Size**: Select "Standard_D2s_v3" for your virtual machine size.

    ![VM Size](../../images/hw5-img2.png)

3. **Licensing**: Choose the option stating that you have a license for trial purposes.

    ![Licensing](../../images/hw5-img3.png)

4. **Disks**: Select "Standard HDD" for disk type.

    ![Disks](../../images/hw5-img4.png)

5. Leave the default settings for Networking, Management, Monitoring, and Advanced tabs.

6. On the "SQL Server Settings" tab, confirm that you have a license.

    ![SQL Server Settings](../../images/hw5-img5.png)

7. Review your selections and proceed with VM creation.

## Step 2: Connecting to the Virtual Machine

After successfully creating the VM, follow the tutorial's instructions for connecting to the virtual machine.

### Note:

- If you're on the BU network, use a VPN connection as port 3389 is blocked on the BU network.
- Mac users should install the "Remote Desktop application from the Apple Store" for connecting. [Link](https://apps.apple.com/us/app/microsoft-remote-desktop/id1295203466?mt=12)

## Step 3: Important Post-Configuration Steps

After connecting to your VM, perform the following actions:

1. **Configure Auto-Shutdown**: Set a time for the VM to automatically shut down when not in use. You can adjust the time based on your preference.

2. **Use "Stop" to Shut Down**: Whenever you finish using the VM, use the "Stop" button to shut down the machine. If prompted to keep the IP address, do so.

3. **Disable IE Enhanced Security Configuration**: In the Virtual Machine's "Server Manager," turn off Internet Explorer Enhanced Security Configuration under "local server."

    ![IE Enhanced Security Configuration](../../images/hw5-img6.png)

    ![IE Enhanced Security Configuration](../../images/hw5-img7.png)

## Step 4: Install Power BI Desktop

Download and install Power BI Desktop (x64) on your VM using your BU email for a trial of the software. You can download it [here](https://powerbi.microsoft.com/en-us/desktop/).

## Additional Notes

- Always be mindful of your Azure resources to avoid unexpected charges.
- Save the VM configuration details and connection information for future reference.

**Happy working with your Azure VM!**
