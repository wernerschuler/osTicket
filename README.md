<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Steps</h2>

Create Virtual Machine in Azure
--- 
- **Create a Resource Group:**
    - Go to portal.azure.com
    - Click Resource groups
    - Click Create
    - Enter the name and region
    - Click Review + create
    - Click Create  <br>

<p>
<img src="https://i.imgur.com/SOEwjm2.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>

- **Create Virtual machine:**
   - Search Virtual machines
   - Click Create, then Azure virtual machine
   - Pick the Resource group you created in the previous step
   - Give the virtual machine a name
   - Set your Region
   - Set your Image to Windows 10
   - Set your Size to 2 vcpus or more
   - Enter a username and password
   - Check the confirm box
   - Click Review + create
   - Click Create

<p>
<img src="https://i.imgur.com/aOgR4s4.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p> <br> <br>

<p>
<img src="https://i.imgur.com/L3vKuMQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p> <br> <br>

<p>
<img src="https://i.imgur.com/VtAimzn.png" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br> <br>
</p>

Installation 
--- 
- **Remote desktop into the virtual machine you created:**
   - Copy the public IP address of the VM
   - Click Start
   - Type and select Remote Desktop Connection
   - Paste the public IP address of the VM
   - Click Connect
   - Click More choices
   - Click Use a different account
   - Enter the username and password you created for this VM
     
<p>
<img src="https://i.imgur.com/lZhuXJ5.png" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br> <br>
</p>

- **Install/ enable Internet Information Services (IIS) with CGI and Common HTTP Features:**
   - From your VM
   - Right click Start
   - Click Run
   - Type Control panel, then click OK
   - Click Programs
   - Click Turn Windows features on or off
   - Check Internet Information Services, then expand it
   - Expand World Wide Web Services
   - Expand Application Development Features
   - Check CGI
   - Collapse Application Development Features
   - Expand Common HTTP Features and check every box
   - Click OK
   - To test the installation go to a web browser and enter 127.0.0.1
 
- **Download and install PHP Manager for IIS:**
   - From your VM
   - Download PHP Manager from: https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view?usp=share_link
   - Once the download is complete go to File Explorer --> Downloads --> PHPManagerForIIS
   - Click Next --> Check I Agree --> Next --> Close
 
- **Download and install the Rewrite module:**
  - Use the link: https://drive.google.com/file/d/1tIK9GZBKj1JyUP87eewxgdNqn9pZmVmY/view?usp=share_link
  - Go to File Explorer --> Downloads --> rewrite_amd64_en-US --> Check Accept --> Install
 
- **Create the Directory C:PHP**
  - Go to File Explorer --> This PC --> Windows (C:)
  - Right Click --> New --> Folder --> Name the folder PHP
 
- **Download PHP and unzip the contents into C:PHP**
   - Download from: https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view?usp=share_link
   - Go to File Explorer --> Downloads --> Right Click the PHP file --> Extract All... --> Browse --> This PC --> Windows (C:) --> PHP --> Select Folder --> Extract
 
- **Download and install Visual C++ Redistributable:**
  - Download from https://drive.google.com/file/d/1s1OsGF3-ioO0_9LYizPRiVuIkb3lFJgH/view?usp=share_link
  - Go File Explorer --> Downloads --> VC_redist.x86 --> Agree --> Install
 
- **Download and install MySQL:**
  - Download MySQL from https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view?usp=share_link
  - When on the setup page --> Next --> Accept --> Next --> Typical --> Install --> Check 'Launch the MySQL Instance Configuration Wizard' --> Finish
  - When on the configuration wizard --> Standard Configuration --> Next --> Enter a password --> Next --> Execute --> Finish
 
- **Open IIS as an Admin:**
- Click Start --> Type IIS --> Right click 'Run as administrator'
- PHP Manager --> Register new PHP version --> Click the symbol with 3 dots --> Windows (C:) --> PHP --> php-cgi --> OK
- Click Restart

- **Install osTicket**
   - Use link https://drive.google.com/file/d/1VeVXKlzHDRjeaVUL99ptq7qYbrbXdFxJ/view?usp=drive_link
   - Go to the osTicket file you just downloaded --> drop the upload file into "c:\inetpub\wwwroot" folder
   - rename upload folder to osTicket
 
- **Restart IIS:**
  - Go to IIS --> Restart

  - Go to Sites --> Default Web Site --> osTicket --> On the right click Browse * 80
  - If done correctly an osTicket page will appear

- **Notice some extenstions are not enabled**
  - Go back to IIS sites --> Default --> osTicket
  - Double-click PHP manager
  - Click Enable or disable and extension
      - Enable php_imap.dll
      - php_intl.dll
      - php_opache.dll
  - Refresh the browser and observe the changes

- **Rename ost-sampleconfig**
 - From: C:inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
 - To: C:inetpub\wwwroot\osTicket\include\ost-config.php

- **Set permissions to ost-config.php**
  - Go to ost-config.php --> Right click, Properties --> Security --> Advanced --> Disable inheritance --> Remove all inherited permissions from this object --> Add --> Select a principal --> Type 'everyone' into box --> Check Names --> OK --> Check 'Full control' --> OK --> Apply --> OK
 
- **Setup osTicket in the browser**
   - Go to osTicket --> Click Continue
   - Add Helpdesk Name & email
   - Add details for Admin user

- **Download and install HeidiSQL**
  - Use link https://docs.google.com/document/d/1WovrX2DaS9xkfaSr4LXyB4YnnWpXIgPCMMbbfgHmGVw/edit
  - Go to Downloads folder --> Click HeidiSQL --> Accept, Next --> Next --> Install --> Check 'Launch HeidiSQL' --> Finish
  - In HeidiSQL --> New --> Enter MySQL username and password --> Open
 
- **In HeidiSQL create a new database**
  - Right click Unnamed --> Create new --> Database --> Enter the name osTicket --> OK
 
- **Continue Setting up osTicket in the broswer**
  - MySQL Database: osTicket
  - Enter MySQL username & password
  - Click Install Now

- **Clean up:**
  - Delete: C:\inetpub\wwwroot\osTicket\setup
  - Set permissions of C:\inetpub\wwwroot\osTicket\include\ost-config.php to Read only:
    - Right click ost-config.php --> Properties --> Security --> Advanced --> Everyone --> Edit --> Uncheck all apart from Read --> OK

- Notes:
  - Link to admin: http://localhost/osTicket/scp/login.php
  - Link to end user: http://localhost/osTicket/
 
Post Installation Setup
--- 

- **If you have not already, login to your VM:**
  - Click Start --> Type and enter Remote Desktop Connection --> Enter the username and password for the VM

- **Bring up the osTicket website:**
  - Copy and paste this URL into a web broswer: http://localhost/osTicket/
  - Login with the credentials you created for osTicket
 
- **Configure roles**
  - Admin panel --> Agents --> Roles --> Add New Role
  - Name: Supreme Admin
  - Permissions --> Tickets --> Check all boxes
  - Tasks --> Check all booxes
  - Knowledgebase --> Check Premade --> Save Changes 

 


 
   

