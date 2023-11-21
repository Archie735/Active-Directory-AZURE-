<p align="center">
<img src=https://github.com/Archie735/Active-Directory-AZURE-/assets/150314129/4322bc56-a0db-415d-876b-1670a8035d98
 alt="Microsoft Active Directory Logo"/>
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


<h2>Ensure connectivity using perpetual ping</h2>

- Open two windows of remote desktop: one for Winterland and the other for Autumn.
    - (In case it may get confusing change the background photos of one or both desktops)
- On the Autumn remote desktop, open the command prompt and ping -t "Winterland's private IP address"

<img src=https://github.com/Archie735/Active-Directory-AZURE-/assets/150314129/c0173412-2a68-4b47-8187-cd0528f7e080 width="80%" height="auto" id="request timed out" alt="">

- In Winterland's remote desktop, on the search bar, type and select "Windows Defender Firewall with Advanced Security"
-  Select "inbound rules" then filter the protocol to view all rules with ICMPv4
-  Right-click and enable Virtual Machine Monitoring and Core Networking Diagnostics (domain and private profile)

<img src=https://github.com/Archie735/Active-Directory-AZURE-/assets/150314129/b952d1a9-d594-4c73-935b-79899eb4db55 width="80%" height="auto" id="inbound rules" alt="">

- The ping is successful if there is a reply

<img src=https://github.com/Archie735/Active-Directory-AZURE-/assets/150314129/2a54629c-b148-4e9b-b184-c5c6472005ad width="80%" height="auto" id="inbound rules" alt="">


<h2>Install Server Manager in Winterland</h2>

- Settings
- Apps
- Optional Features
- Add an optional feature click view features
- Type "server manager" on the search bar
- Check RSAT: Server Manager
- Next
- Install

<img src=https://github.com/Archie735/Active-Directory-AZURE-/assets/150314129/319daa07-88ae-4702-ad98-44242354bc72 width="80%" height="auto" id="Server manager install" alt="">

