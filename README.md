<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This project demonstrates the installation and configuration of the open-source ticketing system **osTicket** to simulate a real-world IT help desk environment.  
This lab replicates what Tier 1 & Tier 2 support technicians typically handle when supporting ticketing infrastructure in small to mid-sized organizations.

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
<img width="1920" height="1080" alt="Screenshot (3)" src="https://github.com/user-attachments/assets/da416d98-5e16-42c6-83f8-e5319b5d96da" />

</>
</p>
<p>
Within the VM install The osTicket installation files using  osTicket-Installation-Files.zip and unzip(extract all files) on to the desktop  we will use the files inside the folder to install osTicket and some of its dependencies. Search up IIS and right-click and run as admin  go to world wide wen services —-- application development features— and enable cgi
</p>
<br />

<p>
<img width="1920" height="1080" alt="Screenshot (8)" src="https://github.com/user-attachments/assets/e3b97de1-6ec5-478f-bc31-3c55564e69c8" />


</p>
<p>
From the inside of osTicket-Installation-Files we will install the dependencies for osTicket first  right click on PHP Manager  after create a directory in the main storage named c:\PHP
Come back to the installation file and right click on rewrite module and install
Next unzip PHP 7.3.8 into the C:\PHP file we just made  install VC redist.x86.exe as well and after download MySQL 5.5.62 — choose typical setup – launch configuration wizard(after install)--- standard configuration – Username: root (just for lab) password: root (just for lab)

</p>
<br />

<p>
<img width="1920" height="1080" alt="Screenshot (15)" src="https://github.com/user-attachments/assets/8281a3eb-71cd-4b4a-9e86-d086e201b788" />

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
<img width="1920" height="1080" alt="Screenshot (23)" src="https://github.com/user-attachments/assets/87fd3839-d4df-438a-ae25-f723d42ec9dd" />

</p>
<p>
Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

 some extensions are not enabled
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
<img width="1920" height="1080" alt="Screenshot (27)" src="https://github.com/user-attachments/assets/de641c3e-43ab-4b1d-ac15-787b99171073" />

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
<img width="1920" height="1080" alt="Screenshot (32)" src="https://github.com/user-attachments/assets/d8c1f4a2-f136-448c-9fd9-2c916de01945" />

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
<img width="1920" height="1080" alt="Screenshot (33)" src="https://github.com/user-attachments/assets/cb8f877d-980a-42c7-8dc9-09ac41a2f0e4" />
</p>
<p>
        Congraluations we completed the lab
</p>        
<br />
