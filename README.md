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

- Install and enable IIS (Internet Information Services) with CGI and common HTTP features.
- Download and install PHP Manager for IIS, the Rewrite Module, and create the directory C:\PHP. Download the PHP zip and extract into C:\PHP.
- Download and install C++ Redistributable
- Download and install MySQL Server Instance.
- Open IIS as an administrator and register new PHP version.
- Install osTicket

<h2>Installation Steps</h2>


![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/3e49c548-29a0-434b-805e-6a7446cd8a1a)



CGI and Common HTTP Features
World Wide Web Services -> Application Development Features ->
[X] CGI
[X] Common HTTP Features
AND IIS Management Console
Internet Information Services -> Web Management Tools -> IIS Management Console
	[X] IIS Management Console
![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/54a4f406-c1cc-4d4f-8ec4-1315608abd61)
- Confirm installation was successful by going to your web browser and searching 127.0.0.1, and you should see the Windows Internet Information Services page appear.
- If unsucessful, uninstall and reinstall.


![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/1396e03b-ab00-4018-bd68-7d9ab396df76)
- Download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
- Download and install the Rewrite Module (rewrite_amd64_en-US.msi)
- Create the directory C:\PHP

![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/37ca2f0b-a521-43c5-8faf-cbd1a591b959)
- Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP

![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/4c3f973c-8d75-4133-ac73-0ea50bcba028)
- Download and install C++ Redistributable

![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/e3b06aff-1b8c-4583-9109-b495f6d7f70f)
- Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration -> Password1 -> Execute
- This is installing a database on the actual computer because osTicket needs somewhere to store application data.

![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/1ddd91a3-4fe4-4415-a828-f20758e59371)
- Open IIS as an administrator and register new PHP version.
- Restart IIS

![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/b040ade3-47a4-42c2-bd52-4ef389883c05)
- Download osTicket from the Installation Files Folder
- Extract and copy “upload” folder to c:\inetpub\wwwroot
- Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”
- Reload IIS, stop and start server.

![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/3d4a6184-071f-4137-be17-f1b39534f4e7)
- Go to view sites -> Default -> osTicket
- On the right, click “Browse *:80
- If there's an error, something went wrong during the lab. If successful, osTicket should appear noting some extensions that are not enabled.
![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/10e92783-7412-4bd6-82a8-d3301f8025ed)

![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/a2e7a245-5cf6-4bec-b534-82a6abfafc89)
- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager
- Click “Enable or disable an extension”
- Enable: php_imap.dll
- Enable: php_intl.dll
- Enable: php_opcache.dll
- Refresh the osTicket site in your browse, observe the changes

![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/e2ae0cac-4902-4247-a135-dfa55ebe3974)
- Rename: ost-config.php
- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php | To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/aaa18d6f-390f-4d89-afd7-54828746dd17)
- Assign Permissions: ost-config.php
- Disable inheritance -> Remove All
- New Permissions -> Everyone -> All

![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/06248f7c-aac9-42f2-bda7-27e5eaa735e8)
- Continue Setting up osTicket in the browser (click Continue)
- Name Helpdesk
- Default email (receives email from customers)

![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/659c5916-b3aa-4a0a-9afe-2c45fc7bfbf5)
- Download and install HeidiSQL
- Open Heidi SQL
- Create a new session, root/Password1
- Connect to the session
- Create a database called “osTicket”

![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/d532500e-15a1-4a10-ad4e-9a2dce5960af)
- Continue Setting up osticket in the browser
- MySQL Database: osTicket
- MySQL Username: root
- MySQL Password: Password1
- Click “Install Now!”
![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/faf74130-b3f5-4fe6-9c4f-f21758f65145)


- Clean Up!
- Delete: C:\inetpub\wwwroot\osTicket\setup
- Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
![image](https://github.com/michaelpeters2/osticket-prereqs/assets/141062110/77bab00b-0e78-4eb6-80cb-38bf0d71f433)
