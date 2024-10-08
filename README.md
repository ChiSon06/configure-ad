<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This project outlines how to install and configure active directory. The install itself will utilize virtual machines, specifically a client and domain controller. The domain controller is where the active directory will be installed, and after the download two different accounts are made, a user and an admin. After that, the client is joined to the domain, and we then setup remote desktop for non-administrative users on it. The final process involves using a random additional user and logging into the client with said user.<br />


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
After this, log back into DC-1 as "mydomain.com\ciadmin", or whatever you chose to name it as.
</p>

<p>
Now, in order to join "Client-1" to "DC-1," go into the Azure Portal and set Client-1's DNS settings to the DC's Private IP Address, then restart it. After that, login to Client-1 as the original local admin and join it to the domain, after the computer has restarted, this is what it should say:
</p>
<img src="https://i.imgur.com/zefTLVJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


<p>
</p>
<p>
Now we're going to setup remote desktop for non-administrative users. To do this, we need to login to Client-1 as mydomain.com\ciadmin(or whatever you chose), and go into system properties and remote desktop. From there, allow "domain users" to access remote desktop. This is shown below:
</p>
<img src="https://i.imgur.com/cHLPcfm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />


<p>
The final part of this project involves a plugin which creates many users and allows me to log back into Client-1 and make sure that I set everything up correctly. I will simply showcase the product of that here:
</p>
<p>
<img src="https://i.imgur.com/bNPvevW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/JMslpw6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

