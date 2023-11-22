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

- Windows 11 Pro(22H2)
- Windows Server 

<h2>Set up Virtual Machines</h2>

Create two virtual machines 

<a href=https://github.com/Archie735/How-to-Create-a-Windows-11-Virtual-Machine/blob/main/README.md> Click here </a> for guidance on how to build a virtual machine.

Information for Virtual Machine 1 (Spring) 🌺 ↓

    Subscription: Azure subscription 1
    Resource group: Create new "Seasons"
    Virtual Machine name: Spring
    Region: (US) East US
    Image: Windows Server 2022 Datacenter: Azure Edition – x64 Gen2
    Size: Standard_E2_v3 – 2 vcpus, 16 GiB memory
    Username: Springtime 
    Password: Springforward4
    Virtual network: Spring-vnet
    Confirm licensing
    Review + Create
    Create

Information for Virtual Machine 2 (Autumn) 🍂↓
(On the network tab, is where you can change the virtual network)

    Subscription: Azure subscription 1
    Resource group: Seasons
    Virtual machine name: Autumn
    Region: (US) East US
    Image: Windows 11 Pro, version 22H2 – x64 Gen 2
    Size: Standard_D4s_v3 - 4vcpus, 16 GiB memory
    Authentication type: Password
    Username: AutumnApple
    Password: Free4falling
    Confirm licensing
    Virtual network: Spring-vnet
    Review + create then Create

<h2> Update Settings on Spring </h2>

- Under Network settings, click on Network Interface
- Under Settings, click on IP configurations then click on the name ipconfig 1
- Change the assignment to "static" then save

  *Static keeps the IP address the same

<img src="https://github.com/Archie735/Active-Directory-AZURE-/assets/150314129/bb78568c-485c-473f-b462-7d32afbc2d56" alt="Spring Network Settings">

<img src="https://github.com/Archie735/Active-Directory-AZURE-/assets/150314129/9e787e6e-7592-4702-bf8e-9bfec159d7ac" alt="Spring IP configurations">

<h2>Ensure connectivity using perpetual ping</h2>

- Open two windows of remote desktop: one for Spring and the other for Autumn.
    - (In case it may get confusing change the background photos of one or both desktops)
- On the Autumn remote desktop, open Windows PowerShell and ping -t "Winterland's private IP address"

<img src=https://github.com/Archie735/Active-Directory-AZURE-/assets/150314129/e1c0d534-15a4-4dde-9b3c-8ff00efb89bf width="80%" height="auto" id="request timed out" alt="Autumn timed out">


- In the Spring's remote desktop, on the search bar, type and select "Windows Defender Firewall with Advanced Security"
-  Select "inbound rules" then filter the protocol to view all rules with ICMPv4
-  Right-click and enable Virtual Machine Monitoring and Core Networking Diagnostics (domain and private profile)

<img src=https://github.com/Archie735/Active-Directory-AZURE-/assets/150314129/2efa88b0-d88c-4e48-9f4e-4a04957d66a2 alt=" Spring defender">


- The ping is successful if there is a reply

<img src=https://github.com/Archie735/Active-Directory-AZURE-/assets/150314129/2b9a332d-1241-4574-bcff-974619d26363 width="80%" height="auto" id="successful ping" alt="Autumn success reply">

<h2>Install Active Directory</h2>
