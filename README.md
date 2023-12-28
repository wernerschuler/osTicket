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
   - Download from the link: https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view?usp=share_link

 
   

