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

- Create a Virtual Machine in Azure
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>

<h3>Create a Vitual Machine in Azure</h3>
<p>
Create the Resource Group
</p>
<p>
<img src="https://i.imgur.com/jfmsee6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create an Azure Windows 10 Virtual Machine (VM), typically with 4 vCPUs Virtual CPUs. 
  
  For the username and password, it can be anything as we'll be using this info to log into the VM with Remote Desktop on our main computer.
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

<h3>Download VC_REDIST</h3>
<p>
From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe. 
</p>
<p>
<img src="https://i.imgur.com/y5ObvUJ.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>Download MySQL</h3>
<p>
From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 
(mysql-5.5.62-win32.msi) – 
</p>
<p>
<img src="https://i.imgur.com/qXF0LED.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Typical Setup -> - - - - 
Launch Configuration Wizard (after install) -> 
Standard Configuration -> 
Username: root,
Password: root
  
  (This will be the Database that osTicket will use to store all our Data in)
</p>
<br />
<p>
<img src="https://i.imgur.com/Rmnpouh.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>Open IIS as an Admin </h3>
<p>
Register PHP from within IIS, click “Register new PHP version” (PHP Manager -> C:\PHP\php-cgi.exe)

  (Here, we are making the Web Server aware of the existence of PHP on the Computer and telling it where it is)
</p>
<p>
<img src="https://i.imgur.com/X2MBRnb.png" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/q1sCY8g.png" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/dD6zauu.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Reload IIS (Open IIS, Stop and Start the server) (on the Right, click Stop, then Start)
</p>
<p>
<img src="https://i.imgur.com/HBH6sme.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>Install osTicket v1.15.8</h3>
<p>
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” 
</p>
<p>
<img src="https://i.imgur.com/FpB0ug9.png" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/9x3WfmM.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now copy the “upload” folder into “c:\inetpub\wwwroot” - 
 
  Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
</p>
<p>
<img src="https://i.imgur.com/woPRquw.png" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Q2cIiaS.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Reload IIS (Open IIS, Stop and Start the server) – Do it Again
  
  Here we are going to load the osTicket site.
  Go to sites -> Default -> osTicket - 
  On the right, click “Browse *:80”
</p>
<p>
<img src="https://i.imgur.com/tXlBKY8.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Note that some extensions are not enabled - 
  
  Go back to IIS, sites -> Default -> osTicket - - - 
  
  Double-click PHP Manager 
  
  Click “Enable or disable an extension” - 
  
  Enable: php_imap.dll - 
  
  Enable: php_intl.dll 
  
  Enable: php_opcache.dll 
</p>
<P>
  <img src="https://i.imgur.com/qKG1BzZ.png" width="80%" alt="Disk Sanitization Steps"/>
</P>
<p>
Refresh the osTicket site in your browser, observe the changes
</p>
<p>
  <img src="https://i.imgur.com/nv3yXOl.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>Rename: ost-config.php </h3>
<p>
  From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php - 
  
  To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
</p>
<p>
  <img src="https://i.imgur.com/pftCwMM.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<h3>Assign Permissions: ost-config.php</h3>
<p>
  Right click to Properties, Security, Advanced,
  
  Disable inheritance -> Remove All – 
</p>
<P>
  <img src="https://i.imgur.com/jKFFIYe.png" width="80%" alt="Disk Sanitization Steps"/>
</P>
<p>
  Next, we’ll add New Permissions, go to add permissions, select a principle, type Everyone 
  
  New Permissions -> Everyone -> All 
  
  (In this lab, we’ll give everyone access to it, just so the Lab can work through the ticket activities)
  
  Then check Full Control
</p>
<p>
  <img src="https://i.imgur.com/ixam2Kx.png" width="80%" alt="Disk Sanitization Steps"/>
  <img src="https://i.imgur.com/vob0Fgn.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Click Apply & OK

 Now osTicket has full control over the configuration file.  
</p>
<br />

<h3>Continue Setting up osTicket in the browser (click Continue)</h3>
<p>
  Name Helpdesk - 
  
  Default email (receives email from customers)
</p>
<p>
  <img src="https://i.imgur.com/Z72pBYq.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Before we continue, since we created the Database Application, we now need to log into that Database and create another database specific to osTicket so we can provide the Database Credentials.
</p>
<br />

<h3>Download and Install HeidiSQL</h3>
<P>
  From the “osTicket-Installation-Files” folder, install HeidiSQL. - 
  
  Open Heidi SQL - - - 
  
  Create a new session, root/root 
  
  Connect to the session 
</P>
<p>
  <img src="https://i.imgur.com/Qdh8xTk.png" width="80%" alt="Disk Sanitization Steps"/>
  <img src="https://i.imgur.com/m9c2BJN.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Create a database called “osTicket”
</p>
<p>
  <img src="https://i.imgur.com/nwjLRWL.png" width="80%" alt="Disk Sanitization Steps"/>
  <img src="https://i.imgur.com/GIYr758.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Continue Setting up osTicket in the browser 
  MySQL Database: osTicket 
  
  MySQL Username: root 
  
  MySQL Password: root 
  
  Click “Install Now!”
</p>
<p>
  <img src="https://i.imgur.com/LJnNroz.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Congratulations, hopefully it is installed with no errors! 
</p>
<p>
  <img src="https://i.imgur.com/Ff3Xmfp.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Here are all the tables of the tables that were created on our osTicket Database, osTicket we use this on the backend to help store our data.
</p>
<p>
  <img src="https://i.imgur.com/XOT6s55.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>Browse your Help Desk Login Page: http://localhost/osTicket/scp/login.php</h3>
<p>
 <img src="https://i.imgur.com/hxRFMne.png" width="80%" alt="Disk Sanitization Steps"/> 
  <img src="https://i.imgur.com/VV9EkWU.png" width="80%" alt="Disk Sanitization Steps"/> 
</p>
<p>
  For End Users, here is the osTicket URL: http://localhost/osTicket/
</p>
