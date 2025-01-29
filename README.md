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

- PHP Manager for IIS
- Rewrite Module
- PHP 7.3.8
- VC_redist.x86
- MySQL 5.5.62
- osTicket v1.15.8
- HeidiSQL

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/ymqCTx5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open the Control Panel and navigate to Programs > Uninstall a Program.
Click on Turn Windows features on or off in the left-hand menu.
In the list of features, expand Internet Information Services > World Wide Web Services > Application Development Features.
Check the box for CGI and click OK.
</p>
<br />

<p>
<img src="https://i.imgur.com/QHSO7f8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install PHP Manager for IIS and then install Rewrite Module.
</p>
<br />

<p>
<img src="https://i.imgur.com/0bqAtLK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a folder named PHP in the C: drive.
</p>
<br />

<p>
<img src="https://i.imgur.com/efvWcoP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
unzip PHP 7.3.8 into the C:PHP folder and then install VC_redist.x86.exe.
</p>
<br />

<p>
<img src="https://i.imgur.com/FgpIgFw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the Configuration Wizard, select Standard Configuration. When you reach the Security Options section, enter root as both the username and password. After the configuration executes successfully, click Finish.
</p>
<br />

<p>
<img src="https://i.imgur.com/NiV2U9m.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open IIS as an administrator. Register PHP in IIS using the path C:\PHP\php-cgi.exe. Afterward, reload IIS by stopping and then restarting the server.
</p>
<br />

<p>
<img src="https://i.imgur.com/t2xgOPe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Unzip osTicket v1.15.8, then copy the upload folder into C:\inetpub\wwwroot. In C:\inetpub\wwwroot, rename the upload folder to osTicket. Finally, open IIS, and restart the server by stopping and starting it.
</p>
<br />

<p>
<img src="https://i.imgur.com/rw9WNlD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open IIS. Navigate to Sites, click on Default Web Site, and then select *Browse :80 on the right-hand side
</p>
<br />

<p>
<img src="https://i.imgur.com/UMpPgUK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Some extensions are not enabled by default. To enable them:

Return to osTicket in IIS.
Double-click PHP Manager.
Select Enable or disable an extension.
Enable the following extensions:
php_imap.dll
php_intl.dll
php_opcache.dll
Refresh the osTicket site in your browser, observe the changes.
</p>
<br />

<p>
<img src="https://i.imgur.com/bx18Uky.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From: C:\inetpub\wwwroot\osTicket\include rename ost-sampleconfig.php to ost-config.php.
</p>
<br />

<p>
<img src="https://i.imgur.com/0S2NilL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Right-click the ost-config.php file and select Properties.
Go to the Security tab and click Advanced.
Click Disable inheritance, then select Remove all inherited permissions from this object.
Click Add, then:
Choose Select a principal.
Enter Everyone and click OK.
Assign Read and Write permissions.
This setup is not secure but is acceptable for testing purposes.
</p>
<br />

<p>
<img src="https://i.imgur.com/BFFafBH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Return to osTicket in your browser and click Continue. Enter the Helpdesk Name and an Email Address to receive customer emails, but do not click Install yet.
</p>
<br />

<p>
<img src="https://i.imgur.com/PiSuU5Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install HeidiSQL and launch the application. Create a new session, using root as the username and password, then click Open.

In the session window:

Right-click on Unnamed.
Select Create New > Database.
Name the new database osTicket.
</p>
<br />

<p>
<img src="https://i.imgur.com/pFmE7Ey.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To continue setting up osTicket:

For MySQL Database, enter: osTicket.
For MySQL Username, enter: root.
For MySQL Password, enter: root.
Finally, click Install Now to complete the setup.
</p>
<br />

<p>
<img src="https://i.imgur.com/ICMpXdg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To clean up after setting up osTicket:

Delete the folder: C:\inetpub\wwwroot\osTicket\setup.
Navigate to C:\inetpub\wwwroot\osTicket\include.
Right-click on ost-config.php, select Properties, go to the Security tab, and set the file permissions to Read-only.
</p>
<br />
