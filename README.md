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

- Windows 10 VM with IIS Installed (with CGI ENABLED)
- PHP Installed and Configured (PHP 7.3.8)
- Database Server (MYSQL 5.5+)
- Required PHP Extensions (php_imap.dll, php_intl.dll, and php_opcache.dll.)
- Administrative Tools (HeidiSQL)

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within the VM install The osTicket installation files using  osTicket-Installation-Files.zip and unzip(extract all files) on to the desktop  we will use the files inside the folder to install osTicket and some of its dependencies. Search up IIS and right-click and run as admin  go to world wide wen services —-- application development features— and enable cgi
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the inside of osTicket-Installation-Files we will install the dependencies for osTicket first  right click on PHP Manager  after create a directory in the main storage named c:\PHP
Come back to the installation file and right click on rewrite module and install
Next unzip PHP 7.3.8 into the C:\PHP file we just made  install VC redist.x86.exe as well and after download MySQL 5.5.62 — choose typical setup – launch configuration wizard(after install)--- standard configuration – Username: root (just for lab) password: root (just for lab)

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open IIS as an Admin Register PHP from within IIS (PHP Manager — C:\PHP\php-cgi.exe) Reload IIS (Open IIS, Stop and Start the server)

Next Install osTicket v1.15.8
From the osTicket-installation-files folder , unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
        Reload IIS (open IIS, stop and the start server)
</p>
<br />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browser, observe the changes


</p>
<br />



<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php 
Assign Permissions: ost-config.php Disable inheritance -> Remove All
New Permissions -> Everyone -> All
Continue Setting up osTicket in the browser (click Continue)
Name Helpdesk
Default email (receives email from customers)

</p>
<br />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the osTicket-installation-files folder  install HEIDISQL
Open Heidi SQL Create a new session, root/rootConnect to the session
Create a database called “osTicket”
Continue Setting up osTicket in the browser
MySQL Database: osTicket  MySQL Username: root  MySQL Password: root Click “Install Now!”

</p>
<br />



<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
