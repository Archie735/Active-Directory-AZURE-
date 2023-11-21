<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows 11 Pro (22H2)

<h2>Prerequisite</h2>

Create two <a href=https://github.com/Archie735/How-to-Create-a-Windows-11-Virtual-Machine/blob/main/README.md>Windows 11 </a> virtual machines that must be in the same virtual network.
In this case, Winterland is virtual machine 1, the resource group will be Seasons. Fill in the information below for Virtual Machine 2, Autumn ↓

    Subscription: Azure subscription 1
    Resource group: Seasons
    Virtual machine name: Autumn
    Region: (US) East US
    Image: Windows 11 Pro, version 22H2 - x64 Gen 2
    Size: Standard_D4s_v3 - 4vcpus, 16 GiB memory
    Authentication type: Password
    Username: AutumnApple
    Password: Free4falling
    Confirm licensing
    Virtual network: Winterland-vnet
    Review + create then Create

<h2> Update Settings on Winterland </h2>

- Under Network settings, click on Network Interface
- Under Settings, click on IP configurations then click on the name ipconfig 1
- Change the assignment to "static" then save

  *Static keeps the IP address the same

<img src=https://github.com/Archie735/Active-Directory-AZURE-/assets/150314129/8e6d1273-fd92-4319-8114-cf9712900c3e width="80%" height="auto" id="static change" alt="">


<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
