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

<h2>Set up Virtual Machines</h2>

Create two Windows 10 virtual machines that must be in the same network. 

<a href=https://github.com/Archie735/How-to-Create-a-Windows-11-Virtual-Machine/blob/main/README.md> Click here </a> to know how to build a virtual machine. Replace the image with Windows 10 Pro, version 22H2 - 64x Gen 2.

Information for Virtual Machine 1 (Winterland) ↓

    Subscription: Azure subscription 1
    Resource group: Create new "Seasons"
    Virtual Machine name: Winterland
    Region: (US) East US
    Image: Windows 10 Pro, version 22H2 - x64 Gen 2
    Size: Standard_D4s_v3 - 4vcpus, 16 GiB memory
    Username: Winterwonderland 
    Password: Winteriscoming2
    Confirm licensing
    Review + Create
    Create

Information for Virtual Machine 2 (Autumn) ↓
(On the network tab, is where you can change the virtual network)

    Subscription: Azure subscription 1
    Resource group: Seasons
    Virtual machine name: Autumn
    Region: (US) East US
    Image: Windows 10 Pro, version 22H2 - 64x Gen 2
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

<img src="https://github.com/Archie735/How-to-Create-a-Windows-11-Virtual-Machine/assets/150314129/38008349-1bfc-4f5e-a0d0-1ad4a3ce4c7a" alt="">

<img src="https://github.com/Archie735/How-to-Create-a-Windows-11-Virtual-Machine/assets/150314129/09587d2a-588b-4e4c-ae14-107fb9e3bc81" alt="">


<h2>Ensure connectivity using perpetual ping</h2>

- Open two windows of remote desktop: one for Winterland and the other for Autumn.
    - (In case it may get confusing change the background photos of one or both desktops)
- On the Autumn remote desktop, open Windows PowerShell and ping -t "Winterland's private IP address"

<img src=https://github.com/Archie735/Active-Directory-AZURE-/assets/150314129/103764bb-8a7b-4722-9ac0-d60ca0d7148f
 width="80%" height="auto" id="request timed out" alt="">

- In Winterland's remote desktop, on the search bar, type and select "Windows Defender Firewall with Advanced Security"
-  Select "inbound rules" then filter the protocol to view all rules with ICMPv4
-  Right-click and enable Virtual Machine Monitoring and Core Networking Diagnostics (domain and private profile)

<img src=https://github.com/Archie735/How-to-Create-a-Windows-11-Virtual-Machine/assets/150314129/8b66d7b6-4562-43ea-b69a-507ffcfaf1f7 width="80%" height="auto" id="inbound rules" alt="">

- The ping is successful if there is a reply

<img src=https://github.com/Archie735/Active-Directory-AZURE-/assets/150314129/85ee0b1b-06d2-403c-9256-2f2557b2f6de
 width="80%" height="auto" id="successful ping" alt="">


<h2>Install Server Manager in Winterland</h2>

- Settings
- Apps
- Optional Features
- Add an optional feature click view features
- Type "server manager" on the search bar
- Check RSAT: Server Manager
- Next
- Install
- Open Server Manager

<img src=https://github.com/Archie735/Active-Directory-AZURE-/assets/150314129/319daa07-88ae-4702-ad98-44242354bc72 width="80%" height="auto" id="Server manager install" alt="">

<img src=https://github.com/Archie735/Active-Directory-AZURE-/assets/150314129/e3fb014a-b7c7-4632-8612-c632ea394797 width="80%" height="auto" id="server manager dashboard" alt="">


