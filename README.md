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
    - Go to portal.azure.com --> Resource groups --> Create
    - Enter a name for the Resource group --> Select Region
    - Review + create --> Create
<p>
<img src="https://i.imgur.com/LFDvGOb.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>

- **Create a Virtual machine:** (example in the images below)
   - Search 'Virtual machines' --> Create --> Azure virtual machine
   - Pick the Resource group you created in the previous step
   - Give the virtual machine a name
   - Set your Region
   - Set your Image to Windows 10
   - Set your Size to 2 vcpus or more
   - Enter a username and password
   - Check the box 'I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights.'
   - Click Review + create
   - Once validation is complete click Create

<p>
<img src="https://i.imgur.com/r7xnE0W.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p> 

<p>
<img src="https://i.imgur.com/kmdac0J.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p> 

Installation 
--- 
- **Remote desktop into the virtual machine you created:**
   - Copy the public IP address of the VM (Virtual machine) --> Start --> Search 'Remote Desktop Connection'
   - Paste public IP address of VM --> More choices --> Use a different account --> Enter the username and password you created for the VM

     
<p>
<img src="https://i.imgur.com/4ta2zJM.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> <br> <br>
</p>

<p>
<img src="https://i.imgur.com/I12PhDC.png" height="60%" width="70%" alt="Disk Sanitization Steps"/> <br> <br>
</p>

- **Install/ enable Internet Information Services (IIS) with CGI and Common HTTP Features:**
   - From your VM --> Right click Start --> Run --> Type Control panel, then click OK --> Click Programs <br>
     
   <img src="https://i.imgur.com/0xKFL9P.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> <br>
   
    - Click Turn Windows features on or off --> Check Internet Information Services, then expand it --> Expand World Wide Web Services <br> --> Expand Application Development Features --> Check CGI

  
  <img src="https://i.imgur.com/tnRlBhc.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> <br> <br>
  
  
   - Collapse Application Development Features --> Expand Common HTTP Features & Check all boxes --> OK
     
   - To test that the installation has worked go to a web browser and enter 127.0.0.1 the browser should take you to a website that looks like the image below.
     
     <img src="https://i.imgur.com/Qjc9OpI.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> 
  <br> 
 
- **Download and install PHP Manager for IIS:** 
   - Copy and paste this link into a web browser in your VM: https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view?usp=share_link
   - Once the download is complete go to File Explorer --> Downloads --> PHPManagerForIIS
   - Click Next --> Check I Agree --> Next --> Close
   - Image below shows the completed installation of PHP Manager
     
     <img src="https://i.imgur.com/OGUaaaH.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
   <br>
 
- **Download and install the Rewrite module:**
  - Copy and paste this link into a web browser in your VM: https://drive.google.com/file/d/1tIK9GZBKj1JyUP87eewxgdNqn9pZmVmY/view?usp=share_link
  - Go to File Explorer --> Downloads --> rewrite_amd64_en-US --> Check Accept --> Install
  - Image below shows the finished installation of the Rewrite module
   
    <img src="https://i.imgur.com/DkGUvw0.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
    <br>
 
- **Create the Directory C:PHP**
  - Go to File Explorer --> This PC --> Windows (C:)
  - Right Click --> New --> Folder --> Name the folder PHP
  - As shown in the image below
    
    <img src="https://i.imgur.com/NonfxWP.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
    <br> <br>
 
- **Download PHP and unzip the contents into C:PHP**
   - Copy and paste this link into a web browser in your VM: https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view?usp=share_link
   - To download all the files, click the symbol highlighted in red in the image below
     
     <img src="https://i.imgur.com/J21xuyu.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
     
   - Go to File Explorer --> Downloads --> Right Click the PHP file --> Extract All... --> Browse --> This PC --> Windows (C:) --> PHP --> Select Folder --> Extract (Pictured below)

     <img src="https://i.imgur.com/YHcjc0h.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
   <br>  
 
- **Download and install Visual C++ Redistributable:**
  - Copy and paste this link into a web browser in your VM: https://drive.google.com/file/d/1s1OsGF3-ioO0_9LYizPRiVuIkb3lFJgH/view?usp=share_link
  - Go File Explorer --> Downloads --> VC_redist.x86 --> Agree --> Install
  - Image below shows the installation is successful
 
    <img src="https://i.imgur.com/zVEOptG.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
    <br> <br>
 
- **Download and install MySQL:**
  - Download MySQL from https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view?usp=share_link
  - When on the setup page --> Next --> Accept --> Next --> Typical --> Install --> Check 'Launch the MySQL Instance Configuration Wizard' --> Finish
  - When on the configuration wizard --> Standard Configuration --> Next --> Enter a password --> Next --> Execute --> Finish
 
    <img src="https://i.imgur.com/fjPZTip.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
    <br> <br>
 
- **Open IIS as an Admin:**
  - Click Start --> Type IIS --> Click 'Run as administrator'
  - PHP Manager --> Register new PHP version --> Click the symbol with 3 dots --> Windows (C:) --> PHP --> php-cgi --> OK
 
    <img src="https://i.imgur.com/UdVn1nr.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

    <img src="https://i.imgur.com/bPbhTEH.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
  - Click Restart ***Maybe get rid**

- **Install osTicket**
   - Use link https://drive.google.com/file/d/1VeVXKlzHDRjeaVUL99ptq7qYbrbXdFxJ/view?usp=drive_link
   - Go to the osTicket file you just downloaded --> drag and drop the upload file into "c:\inetpub\wwwroot" folder 

     <img src="https://i.imgur.com/VNw5jrg.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
  
   - rename upload folder to osTicket
 
     <img src="https://i.imgur.com/8mc9ZwZ.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
 
- **Restart IIS:**
  - Click Start --> Type IIS --> Click'Run as administrator' --> Click Restart
    
    <img src="https://i.imgur.com/RY87upx.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

  - Go to Sites --> Default Web Site --> osTicket --> On the right click Browse * 80

    <img src="https://i.imgur.com/hteVZeB.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
     
  - If done correctly an osTicket page will appear like the image below
 
    <img src="https://i.imgur.com/bvnFuBR.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

- **Notice some extenstions are not enabled**
  - Go back to IIS sites --> Default --> osTicket
  - Double-click PHP manager
  - Click Enable or disable an extension
      - Enable php_imap.dll
      - php_intl.dll
      - php_opache.dll
  - Refresh the browser and observe the changes

- **Rename ost-sampleconfig**
  - From: C:inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
  - To: C:inetpub\wwwroot\osTicket\include\ost-config.php
 
    <img src="https://i.imgur.com/nmNgpuM.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

- **Set permissions to ost-config.php**
  - Go to ost-config.php --> Right click, Properties --> Security --> Advanced --> Disable inheritance --> Remove all inherited permissions from this object --> Add --> Select a principal --> Type 'everyone' into box --> Check Names --> OK --> Check 'Full control' --> OK --> Apply --> OK
 
    <img src="https://i.imgur.com/FTQLx9V.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

    <img src="https://i.imgur.com/loVp181.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
 
- **Setup osTicket in the browser**
   - Go to osTicket --> Click Continue
   - Add Helpdesk Name & email
   - Add details for Admin user

    <img src="https://i.imgur.com/bPuq29x.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>



- **Download and install HeidiSQL**
  - Copy and paste this link to a browser in the VM: https://docs.google.com/document/d/1WovrX2DaS9xkfaSr4LXyB4YnnWpXIgPCMMbbfgHmGVw/edit
  - Go to Downloads folder --> Click HeidiSQL --> Accept, Next --> Next --> Next --> Next --> Next --> Install --> Check 'Launch HeidiSQL' --> Finish
  - In HeidiSQL --> New --> Enter MySQL username and password --> Open

    <img src="https://i.imgur.com/3PBbJ2p.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
 
- **In HeidiSQL create a new database**
  - Right click Unnamed --> Create new --> Database --> Enter the name osTicket --> OK
 
    <img src="https://i.imgur.com/pBSgXEC.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
 
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

- **Configure a department**
  - Admin panel --> Agents --> Departments --> Add New Department
  - Give the department a name
  - Create the department with default settings
 
- **Configure teams**
  - Admin panel --> Agents --> Teams --> Add New Team
  - A the team name --> Members --> Select Agent --> Add a member --> Create Team
 
- **Permit anyone to generate tickets**
  - Admin panel --> Settings --> Users
  - Make sure 'Require registration and login to create tickets' is unchecked
 
- **Configure Agents**
  - Admin panel --> Agents --> Add New Agent
  - Give the agent a name --> Email address --> Username --> Password --> Uncheck 'Send the agent a password reset email' and 'Require password change at next login' --> Set
  - Teams --> Select a team --> Add --> Create  

- **Configure Users**
  - Agent Panel --> Users --> Add User
  - Enter user detail --> Add User
 
- **Configure Service level agreement (SLA)**
  - Admin Panel --> Manage --> SLA --> Add New SLA Plan
  - Enter SLA information --> Add Plan
 
- **Configure Help Topics**
  - Admin Panel --> Manage --> Help Topics --> Add New Help Topic
  - Enter help topic information --> Add Topic
***when doing it yourself give 1 or 2 e.g.***

- **Tickets and Ticket Lifecycle**
  

 


 
   

