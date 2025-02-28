<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source Help Desk Ticketing System osTicket.<br />

<h2>Software and Technologies Used</h2>

- Windows 10 Pro, (version 22H2)
- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 Pro </b> (22H2)

<h2>Prerequisites</h2>

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>

<h3>Create a Vitual Machine in Azure</h3>

Create the Resource Group

<p>
<img src="https://i.imgur.com/jfmsee6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create an Azure Windows 10 Virtual Machine (VM), typically with 4 vCPUs Virtual CPUs. For the username and password, it can be anything as we'll be using this info to log into the VM with Remote Desktop on our main computer.
</p>
<br />

<p>
<img src="https://i.imgur.com/r5BZvef.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
After creating, log into the Azure VM with Remote Desktop on your PC,
</p>
<br />

<p>
<img src="https://i.imgur.com/R9TZyBT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now from within the VM (osticket-vm), download the osTicket-Installation-Files.zip and unzip or extract it onto your desktop. The folder should be called “osTicket-Installation-Files”.
  
-We will use the files in this folder to install osTicket and some of the Dependencies it needs to run.
</p>
<br />

<p>
<img src="https://i.imgur.com/26QLMMD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Next, we are going to Install / Enable IIS (Internet Information Services, a web server that will serve osTicket) in Windows WITH CGI. 

  Go to your Search Bar > Type "Control Panel" > Click "Programs" > "Turn Windows features on or off" > Scroll down to "Internet Information Services (IIS).

-World Wide Web Services -> Application Development Features -> [X] CGI
</p>
<br />

<p>
<img src="https://i.imgur.com/JWhTHzv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>Install PHP Manager</h3>
<p>
Next, From the “osTicket-Installation-Files” folder, install PHP Manager for IIS 
(PHPManagerForIIS_V1.5.0.msi)
</p>
<p>
<img src="https://i.imgur.com/zfPLpZC.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>Install Rewrite Module</h3>
<p>
Next, From the “osTicket-Installation-Files” folder install the Rewrite Module 
(rewrite_amd64_en-US.msi) 
</p>
<p>
<img src="https://i.imgur.com/Sdj6eJR.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>Create DIRECTORY C:\PHP</h3>
<p>
Open File Explorer, type, "C:\" in the search bar, Right-click and create a new folder called, "PHP".

  From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 
(php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder.
</p>
<p>
<img src="https://i.imgur.com/DSdpGPO.png" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/kV7y6yf.png" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/UcB7eYS.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
