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

- Windows Server 2022
- Windows 10 (21H2)

<h2>Pre-Active Directory Requirements</h2>

- Using Microsoft Azure, create two virtual machines. Create a Domain Controller VM (in this case, I made one named "DC-1"), and take note of the Vnet created. 
- Set the Domain Controller's NIC Private IP address to be static
- Create a Client VM (in this case, the one I made is named "Client-1"), use the same resource group and Vnet that was created with the domain controller.
<img src="https://i.imgur.com/rEmcPp5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<h2>High-Level Deployment and Configuration Steps</h2>

- Install Active Directory
- Create an Admin and Normal User Account in AD
- Join Client-1 to Domain
- Setup Remote Desktop for non-administrative users on Client-1
- Create a bunch of additional users and attempt to log into client-1 with one the new users

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/80aGWjJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Above is the first step once in the DC-1 Domain Controller. After successfully logging in, its now time to deploy the domain. For this instance, I made the domain with the name "mydomain.com". After going through the config wizard for that, restart and log back in under "mydomain.com/(whatever name was created for the DC-1 originally)".
</p>
<br />

<p>
</p>
<p>
We will now create two different Organizational Units: _EMPLOYESS and _ADMINS. These will be used to seperate employees within the company based on admin status or employee status.
</p>
<img src="https://i.imgur.com/Qu9z0KB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
After this, in the _ADMINS folder we just created, we will create an admin user, in this case, I named mine "christian ison," or "ciadmin."
</p>
<img src="https://i.imgur.com/emT0PQ5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
